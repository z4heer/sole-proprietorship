Perfect! Let me provide you with a complete manual setup guide for building your management platform with Angular and Python.

---

# 🚀 Complete Setup Guide: Angular + Python Management Platform

## **Part 1: Project Structure Setup**

### Step 1: Create Main Directory
```bash
cd ~
mkdir sole-proprietorship-platform
cd sole-proprietorship-platform
```

### Step 2: Initialize Git Repository
```bash
git init
git config user.name "Your Name"
git config user.email "your-email@example.com"
git remote add origin https://github.com/z4heer/sole-proprietorship.git
```

### Step 3: Create Project Folder Structure
```bash
# Frontend (Angular)
mkdir -p frontend/src/{app,assets,environments}
mkdir -p frontend/src/app/{components,services,models,modules}

# Backend (Python)
mkdir -p backend/{app,config,models,routes,services,utils}
mkdir -p backend/{logs,migrations,tests}

# Documentation
mkdir -p docs/{setup,api,features}

# Configuration
mkdir -p config
```

**Result Structure:**
```
sole-proprietorship-platform/
├── frontend/                 # Angular app
├── backend/                  # Python API
├── docs/                     # Documentation
├── config/                   # Shared configs
└── .gitignore
```

---

## **Part 2: Backend Setup (Python)**

### Step 1: Create Python Virtual Environment
```bash
cd backend

# Windows
python -m venv venv
venv\Scripts\activate

# Mac/Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 2: Create requirements.txt
Create file: `backend/requirements.txt`

```
Flask==2.3.0
Flask-CORS==4.0.0
Flask-SQLAlchemy==3.0.0
python-dotenv==1.0.0
PyJWT==2.6.0
bcrypt==4.0.0
psycopg2-binary==2.9.0
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Create Main App File
Create file: `backend/app.py`

```python
from flask import Flask, jsonify
from flask_cors import CORS
from flask_sqlalchemy import SQLAlchemy
import os
from dotenv import load_dotenv

load_dotenv()

app = Flask(__name__)
CORS(app)

# Database Configuration
app.config['SQLALCHEMY_DATABASE_URI'] = os.getenv(
    'DATABASE_URL', 
    'sqlite:///proprietorship.db'
)
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
app.config['SECRET_KEY'] = os.getenv('SECRET_KEY', 'dev-secret-key')

db = SQLAlchemy(app)

# Health Check Route
@app.route('/api/health', methods=['GET'])
def health():
    return jsonify({'status': 'Backend is running', 'version': '1.0.0'}), 200

if __name__ == '__main__':
    with app.app_context():
        db.create_all()
    app.run(debug=True, host='0.0.0.0', port=5000)
```

### Step 5: Create Environment File
Create file: `backend/.env`

```
FLASK_ENV=development
FLASK_DEBUG=True
DATABASE_URL=sqlite:///proprietorship.db
SECRET_KEY=your-secret-key-change-in-production
JWT_SECRET=your-jwt-secret-key
```

### Step 6: Create Models File
Create file: `backend/models.py`

```python
from app import db
from datetime import datetime

class User(db.Model):
    __tablename__ = 'users'
    
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(80), unique=True, nullable=False)
    email = db.Column(db.String(120), unique=True, nullable=False)
    password = db.Column(db.String(255), nullable=False)
    created_at = db.Column(db.DateTime, default=datetime.utcnow)
    
    def __repr__(self):
        return f'<User {self.username}>'

class Operation(db.Model):
    __tablename__ = 'operations'
    
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(100), nullable=False)
    description = db.Column(db.Text)
    status = db.Column(db.String(50), default='active')
    user_id = db.Column(db.Integer, db.ForeignKey('users.id'), nullable=False)
    created_at = db.Column(db.DateTime, default=datetime.utcnow)
    updated_at = db.Column(db.DateTime, default=datetime.utcnow, onupdate=datetime.utcnow)
    
    def __repr__(self):
        return f'<Operation {self.name}>'

class Task(db.Model):
    __tablename__ = 'tasks'
    
    id = db.Column(db.Integer, primary_key=True)
    title = db.Column(db.String(200), nullable=False)
    description = db.Column(db.Text)
    operation_id = db.Column(db.Integer, db.ForeignKey('operations.id'), nullable=False)
    status = db.Column(db.String(50), default='pending')
    priority = db.Column(db.String(20), default='medium')
    due_date = db.Column(db.DateTime)
    completed_at = db.Column(db.DateTime)
    created_at = db.Column(db.DateTime, default=datetime.utcnow)
    
    def __repr__(self):
        return f'<Task {self.title}>'
```

### Step 7: Create Routes File
Create file: `backend/routes.py`

```python
from flask import Blueprint, request, jsonify
from app import db
from models import User, Operation, Task
from datetime import datetime

api = Blueprint('api', __name__, url_prefix='/api')

# Operations Routes
@api.route('/operations', methods=['GET'])
def get_operations():
    operations = Operation.query.all()
    return jsonify([{
        'id': op.id,
        'name': op.name,
        'description': op.description,
        'status': op.status
    } for op in operations]), 200

@api.route('/operations', methods=['POST'])
def create_operation():
    data = request.get_json()
    operation = Operation(
        name=data.get('name'),
        description=data.get('description'),
        user_id=1  # Change based on auth
    )
    db.session.add(operation)
    db.session.commit()
    return jsonify({'id': operation.id, 'message': 'Operation created'}), 201

# Tasks Routes
@api.route('/tasks', methods=['GET'])
def get_tasks():
    tasks = Task.query.all()
    return jsonify([{
        'id': task.id,
        'title': task.title,
        'status': task.status,
        'priority': task.priority
    } for task in tasks]), 200

@api.route('/tasks', methods=['POST'])
def create_task():
    data = request.get_json()
    task = Task(
        title=data.get('title'),
        description=data.get('description'),
        operation_id=data.get('operation_id'),
        priority=data.get('priority', 'medium')
    )
    db.session.add(task)
    db.session.commit()
    return jsonify({'id': task.id, 'message': 'Task created'}), 201

@api.route('/tasks/<int:task_id>', methods=['PUT'])
def update_task(task_id):
    task = Task.query.get_or_404(task_id)
    data = request.get_json()
    task.status = data.get('status', task.status)
    task.completed_at = datetime.utcnow() if data.get('status') == 'completed' else task.completed_at
    db.session.commit()
    return jsonify({'message': 'Task updated'}), 200
```

### Step 8: Update app.py to Include Routes
Edit `backend/app.py` and add before `if __name__`:

```python
from routes import api
app.register_blueprint(api)
```

### Step 9: Test Backend
```bash
python app.py
```

Visit: `http://localhost:5000/api/health`

You should see: `{"status": "Backend is running", "version": "1.0.0"}`

---

## **Part 3: Frontend Setup (Angular)**

### Step 1: Install Node.js & npm
Download from: https://nodejs.org/ (LTS version recommended)

Verify installation:
```bash
node --version
npm --version
```

### Step 2: Install Angular CLI
```bash
npm install -g @angular/cli
```

### Step 3: Create Angular Project
```bash
cd frontend
ng new sole-proprietorship-app --routing --style=css
cd sole-proprietorship-app
```

Or manual setup:

```bash
npm init -y
npm install @angular/core @angular/common @angular/platform-browser @angular/platform-browser-dynamic @angular/router @angular/forms
```

### Step 4: Create Angular Component Structure
```bash
ng generate component components/dashboard
ng generate component components/operations
ng generate component components/tasks
ng generate component components/sidebar
ng generate component components/header

ng generate service services/api
ng generate service services/operations
ng generate service services/tasks
```

### Step 5: Create API Service
Create file: `frontend/src/app/services/api.service.ts`

```typescript
import { Injectable } from '@angular/core';
import { HttpClient, HttpHeaders } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class ApiService {
  private apiUrl = 'http://localhost:5000/api';

  constructor(private http: HttpClient) { }

  private getHeaders(): HttpHeaders {
    return new HttpHeaders({
      'Content-Type': 'application/json'
    });
  }

  // Operations
  getOperations(): Observable<any> {
    return this.http.get(`${this.apiUrl}/operations`);
  }

  createOperation(operation: any): Observable<any> {
    return this.http.post(`${this.apiUrl}/operations`, operation, {
      headers: this.getHeaders()
    });
  }

  // Tasks
  getTasks(): Observable<any> {
    return this.http.get(`${this.apiUrl}/tasks`);
  }

  createTask(task: any): Observable<any> {
    return this.http.post(`${this.apiUrl}/tasks`, task, {
      headers: this.getHeaders()
    });
  }

  updateTask(taskId: number, task: any): Observable<any> {
    return this.http.put(`${this.apiUrl}/tasks/${taskId}`, task, {
      headers: this.getHeaders()
    });
  }

  // Health Check
  healthCheck(): Observable<any> {
    return this.http.get(`${this.apiUrl}/health`);
  }
}
```

### Step 6: Create Dashboard Component
Create file: `frontend/src/app/components/dashboard/dashboard.component.ts`

```typescript
import { Component, OnInit } from '@angular/core';
import { ApiService } from '../../services/api.service';

@Component({
  selector: 'app-dashboard',
  templateUrl: './dashboard.component.html',
  styleUrls: ['./dashboard.component.css']
})
export class DashboardComponent implements OnInit {
  operations: any[] = [];
  tasks: any[] = [];
  loading = true;
  backendStatus = 'Checking...';

  constructor(private apiService: ApiService) { }

  ngOnInit(): void {
    this.checkBackend();
    this.loadOperations();
    this.loadTasks();
  }

  checkBackend(): void {
    this.apiService.healthCheck().subscribe(
      (response) => {
        this.backendStatus = '✅ Backend Connected';
      },
      (error) => {
        this.backendStatus = '❌ Backend Disconnected';
      }
    );
  }

  loadOperations(): void {
    this.apiService.getOperations().subscribe(
      (data) => {
        this.operations = data;
        this.loading = false;
      },
      (error) => {
        console.error('Error loading operations:', error);
        this.loading = false;
      }
    );
  }

  loadTasks(): void {
    this.apiService.getTasks().subscribe(
      (data) => {
        this.tasks = data;
      },
      (error) => {
        console.error('Error loading tasks:', error);
      }
    );
  }

  createNewOperation(): void {
    const newOp = {
      name: 'New Operation',
      description: 'Description here'
    };
    this.apiService.createOperation(newOp).subscribe(
      (response) => {
        this.loadOperations();
      }
    );
  }
}
```

Create file: `frontend/src/app/components/dashboard/dashboard.component.html`

```html
<div class="dashboard">
  <h1>Sole Proprietorship Management Dashboard</h1>
  
  <div class="status-card">
    <p>Backend Status: {{ backendStatus }}</p>
  </div>

  <div class="stats">
    <div class="stat-card">
      <h3>Operations</h3>
      <p class="number">{{ operations.length }}</p>
    </div>
    <div class="stat-card">
      <h3>Active Tasks</h3>
      <p class="number">{{ tasks.length }}</p>
    </div>
  </div>

  <button (click)="createNewOperation()" class="btn-primary">
    + New Operation
  </button>

  <div *ngIf="loading" class="loading">Loading...</div>

  <div *ngIf="!loading" class="operations-list">
    <h2>Operations</h2>
    <ul>
      <li *ngFor="let op of operations">
        {{ op.name }} - {{ op.status }}
      </li>
    </ul>
  </div>
</div>
```

Create file: `frontend/src/app/components/dashboard/dashboard.component.css`

```css
.dashboard {
  padding: 20px;
  max-width: 1200px;
  margin: 0 auto;
}

.status-card {
  background: #f0f0f0;
  padding: 15px;
  border-radius: 5px;
  margin-bottom: 20px;
  border-left: 4px solid #007bff;
}

.stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  margin-bottom: 30px;
}

.stat-card {
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  text-align: center;
}

.stat-card h3 {
  color: #666;
  margin: 0 0 10px 0;
}

.stat-card .number {
  font-size: 32px;
  font-weight: bold;
  color: #007bff;
  margin: 0;
}

.btn-primary {
  background: #007bff;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  margin-bottom: 20px;
}

.btn-primary:hover {
  background: #0056b3;
}

.operations-list ul {
  list-style: none;
  padding: 0;
}

.operations-list li {
  padding: 10px;
  background: #f9f9f9;
  margin-bottom: 10px;
  border-radius: 4px;
  border-left: 3px solid #007bff;
}

.loading {
  text-align: center;
  padding: 40px;
  font-size: 18px;
  color: #666;
}
```

### Step 7: Update App Module
Edit `frontend/src/app/app.module.ts`

```typescript
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { HttpClientModule } from '@angular/common/http';
import { FormsModule } from '@angular/forms';

import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { DashboardComponent } from './components/dashboard/dashboard.component';

@NgModule({
  declarations: [
    AppComponent,
    DashboardComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    HttpClientModule,
    FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

### Step 8: Update App Component
Edit `frontend/src/app/app.component.html`

```html
<div class="app-container">
  <app-dashboard></app-dashboard>
</div>
```

### Step 9: Test Frontend
```bash
ng serve
```

Visit: `http://localhost:4200`

---

## **Part 4: Run Both Together**

### Terminal 1: Backend
```bash
cd backend
source venv/bin/activate  # or venv\Scripts\activate on Windows
python app.py
```

Backend runs on: `http://localhost:5000`

### Terminal 2: Frontend
```bash
cd frontend/sole-proprietorship-app
ng serve
```

Frontend runs on: `http://localhost:4200`

---

## **Part 5: Git Push to GitHub**

```bash
# Go to root directory
cd sole-proprietorship-platform

# Create .gitignore
cat > .gitignore << EOF
# Backend
backend/venv/
backend/__pycache__/
backend/*.pyc
backend/.env
backend/*.db

# Frontend
frontend/node_modules/
frontend/dist/
frontend/.angular/

# IDE
.vscode/
.idea/
*.swp
EOF

# Add all files
git add .
git commit -m "Initial: Angular + Python management platform"

# Push to GitHub
git branch -M main
git push -u origin main
```

---

## **✅ Checklist**

- [ ] Backend virtual environment created
- [ ] Backend dependencies installed
- [ ] Backend app.py running on port 5000
- [ ] Frontend Angular project created
- [ ] Frontend components generated
- [ ] API service created
- [ ] Dashboard component working
- [ ] Frontend running on port 4200
- [ ] Backend and frontend connected
- [ ] Files pushed to GitHub

---

**Ready to execute?** Start with **Part 1** and let me know when you complete each section! 🚀
