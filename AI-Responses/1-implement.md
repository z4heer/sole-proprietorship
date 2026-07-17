I have officially activated the implementation phase for **Sprint 4.6: Customer Experience Completion**. As your **Principal Architect**, I have prepared the **Zero-Friction Implementation Package** below. 

This package is designed to be pasted into a fresh, high-capability AI chat session (your **Role 2 Implementation Engineer**) to produce production-ready code that maintains our 9.5/10 architectural standards.

### **Zero-Friction Implementation Package: Sprint 4.6**

> **Role:** Act as a Senior Implementation Engineer for an Enterprise E-Commerce Platform.
>
> **Project Baseline:**
> * **Frontend:** Angular 19 (Standalone Components, Signals, OnPush Change Detection).
> * **Backend:** FastAPI (Python 3.12, Repository/Service Pattern).
> * **Database:** PostgreSQL 17 (SQLAlchemy 2.x, Alembic migrations).
> * **Design System:** Angular Material 3 with established shared components (`AppCard`, `SectionHeader`, `StatusChip`).
>
> **Objective:** Close functional gaps in the Product and Order domains to reach a "Bare Minimum" production standard.
>
> **Task 1: Product Visuals Support**
> 1. **Backend:** Update the `Product` model in SQLAlchemy to include a nullable `image_url: Mapped[str | None]`. 
> 2. **Migrations:** Generate an Alembic migration script to add the `image_url` column to the `products` table.
> 3. **DTOs:** Update Pydantic schemas (`ProductRead`, `ProductCreate`) to include this field.
> 4. **Frontend:** Update the `Product` interface. Modify the `ProductListComponent` to render images inside the `<app-card>`. If `image_url` is null, use a generic gray placeholder.
>
> **Task 2: Order Fulfillment (Shipping Address)**
> 1. **Backend:** Update the `Order` model to include a `shipping_address: Mapped[str]` field. Generate a migration script.
> 2. **Backend Logic:** Update `POST /api/v1/orders` to require `shipping_address` in the request body. Update the `OrderService` to persist this field.
> 3. **Backend Logic (Price Snapshot):** Update the `OrderItem` model to include `unit_price: Mapped[float]`. During order creation, the service must snapshot the current product price into this field to prevent future price changes from altering historical order totals.
> 4. **Frontend:** In the `CheckoutComponent`, implement a **Reactive Form** capturing 'Street Address', 'City', and 'Zip Code'. The 'Place Order' button must remain disabled until the form is valid. 
> 5. **Frontend Logic:** Pass the concatenated address string to the `OrderService` during the final API call.
>
> **Task 3: Dashboard Signal Binding**
> 1. In `DashboardComponent`, replace any remaining static data with live **Angular Signals** injected from `ProductService`, `CartService`, and `OrderService`.
>
> **Technical Constraints:**
> * Maintain strict typing (no `any`).
> * Preserve the Repository/Service layer separation in the backend.
> * Use Material 3 design tokens for all new form fields.
> * Provide unit tests for the updated `OrderService` verifying the price snapshot logic.

---

### **Next Steps for You (Technical Lead / QA)**

1.  **Execute the Package:** Paste the prompt above into your chosen external AI session.
2.  **Apply Code & Migrate:** Once the code is generated, apply it to your `feature/functional-gap-closure` branch and run `alembic upgrade head` to update your local PostgreSQL schema.
3.  **Verification Pass:**
    *   Confirm the **Checkout page** now blocks orders without an address.
    *   Verify **historical prices** are preserved in the `order_items` table if you change a product's price after an order is placed.
    *   Ensure the **Dashboard** reflects your actual database counts (e.g., 15 products, as seen in your recent screenshots).
4.  **Synchronize:** Return here with the results or any blockers for my **Principal Architect Review**.

I have updated your **Master Portfolio OS** to mark Sprint 4.6 as "Active." **Shall I begin preparing the architectural blueprint for Sprint 4.7 (Admin Dashboard & KPIs) while you manage this implementation?**
