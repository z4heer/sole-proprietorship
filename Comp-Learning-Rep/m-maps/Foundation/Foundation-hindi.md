# Computer Fundamentals

## CPU (Processor)

### CPU kya hai

CPU computer ka brain hota hai.
Ye instructions process karta hai.

### Iska use kisliye hota hai

* Programs run karne ke liye
* Calculations karne ke liye
* OS aur applications control karne ke liye

### Ye internally kaise kaam karta hai

CPU instructions fetch karta hai → decode karta hai → execute karta hai.

### Working Steps

Program start → Instruction RAM se fetch → CPU process → Result memory me save

### Mental Image / Analogy

CPU ko factory manager samjho.
Sab workers ko instructions deta hai.

### Real Engineer Usage

* Performance troubleshooting
* Server sizing
* High CPU issue analysis

### Common Commands or Tools

Linux:

```bash
top
htop
lscpu
```

### Troubleshooting Thinking

* System slow?
* CPU 100%?
* Kaunsa process CPU kha raha hai?

### Communication Practice

* “CPU system instructions execute karta hai.”
* “High CPU mostly heavy process ya infinite loop ki wajah se hota hai.”
* “CPU utilization monitoring production systems me important hota hai.”

---

## RAM (Memory)

### RAM kya hai

Temporary working memory hoti hai.

### Iska use kisliye hota hai

Running applications ka active data store karne ke liye.

### Ye internally kaise kaam karta hai

Application open → Data RAM me load → CPU directly access karta hai.

### Working Steps

App start → RAM allocation → CPU access → App close → Memory free

### Mental Image / Analogy

RAM ko office desk samjho.
Jitni badi desk, utna zyada kaam ek saath.

### Real Engineer Usage

* Memory leak detection
* Server tuning
* JVM memory sizing

### Common Commands

```bash
free -h
top
vmstat
```

### Troubleshooting Thinking

* System hang?
* Swap use ho raha?
* RAM full?

### Communication Practice

* “RAM temporary active memory hoti hai.”
* “Low RAM system performance ko impact karta hai.”
* “Applications runtime data RAM me store karte hain.”

---

## Storage (HDD/SSD)

### Storage kya hai

Permanent data storage.

### Iska use kisliye hota hai

OS, files, applications store karne ke liye.

### Ye internally kaise kaam karta hai

Data blocks me disk pe save hota hai.

### Working Steps

File save → Filesystem organize → Disk write → Future read

### Mental Image / Analogy

Storage ko warehouse samjho.

### Real Engineer Usage

* Disk management
* Backup handling
* Log storage analysis

### Common Commands

```bash
df -h
du -sh *
lsblk
```

### Troubleshooting Thinking

* Disk full?
* Slow IO?
* Logs huge size le rahe?

### Communication Practice

* “SSD HDD se faster hota hai.”
* “Disk space monitoring production me critical hota hai.”
* “Filesystem data organization handle karta hai.”

---

# Linux Fundamentals

## Linux OS

### Linux kya hai

Open-source operating system.

### Iska use kisliye hota hai

* Servers
* Cloud systems
* DevOps
* Containers

### Ye internally kaise kaam karta hai

Kernel hardware aur software ke beech bridge ka kaam karta hai.

### Working Steps

Bootloader → Kernel load → Services start → User login

### Mental Image / Analogy

Linux ko building management system samjho.

### Real Engineer Usage

* Server administration
* Deployment
* Monitoring
* Automation

### Common Commands

```bash
pwd
ls
cd
mkdir
rm
cp
mv
```

### Troubleshooting Thinking

* Service chal rahi?
* Permission issue?
* Resource issue?

### Communication Practice

* “Linux server environments me widely use hota hai.”
* “CLI operations automation ko easy banate hain.”
* “Linux troubleshooting logs aur processes se start hoti hai.”

---

## File System

### File System kya hai

Data organize karne ka structure.

### Iska use kisliye hota hai

Files aur folders manage karne ke liye.

### Ye internally kaise kaam karta hai

Files inodes aur blocks me map hoti hain.

### Working Steps

File create → Metadata assign → Disk block allocate → Access

### Mental Image / Analogy

Library shelf system.

### Real Engineer Usage

* Log management
* Storage troubleshooting
* Mount management

### Common Commands

```bash
ls
tree
find
mount
df -h
```

### Troubleshooting Thinking

* Mount missing?
* Permission denied?
* Disk corruption?

### Communication Practice

* “Linux filesystem hierarchical structure use karta hai.”
* “Permissions aur mounts filesystem management me important hain.”

---

## Permissions

### Permissions kya hai

Access control mechanism.

### Iska use kisliye hota hai

Security maintain karne ke liye.

### Ye internally kaise kaam karta hai

User/group basis pe read-write-execute control hota hai.

### Working Steps

User request → Permission check → Access allow/deny

### Mental Image / Analogy

Room access card system.

### Real Engineer Usage

* Secure deployments
* User access control
* SSH key security

### Common Commands

```bash
chmod
chown
ls -l
```

### Troubleshooting Thinking

* Permission denied?
* Wrong ownership?
* Execute permission missing?

### Communication Practice

* “Linux permissions security ke liye critical hain.”
* “Ownership aur permission issues common troubleshooting area hain.”

---

# Networking Basics

## IP Address

### IP Address kya hai

Network device ka unique address.

### Iska use kisliye hota hai

Devices ko identify karne ke liye.

### Ye internally kaise kaam karta hai

Packets source IP se destination IP tak route hote hain.

### Working Steps

Request create → Packet route → Destination receive → Response return

### Mental Image / Analogy

Home address system.

### Real Engineer Usage

* Server connectivity
* Firewall rules
* Routing troubleshooting

### Common Commands

```bash
ip a
ifconfig
ping
```

### Troubleshooting Thinking

* IP assigned?
* Network reachable?
* Wrong subnet?

### Communication Practice

* “IP address network identity provide karta hai.”
* “Connectivity testing ping se quickly verify hoti hai.”

---

## DNS

### DNS kya hai

Domain ko IP me convert karta hai.

### Iska use kisliye hota hai

Human-friendly names use karne ke liye.

### Ye internally kaise kaam karta hai

DNS server domain lookup karta hai.

### Working Steps

Domain request → DNS lookup → IP return → Connection establish

### Mental Image / Analogy

Phone contact list.

### Real Engineer Usage

* Website troubleshooting
* Internal service discovery
* Cloud networking

### Common Commands

```bash
nslookup google.com
dig google.com
```

### Troubleshooting Thinking

* DNS resolve ho raha?
* Wrong DNS server?
* Cache issue?

### Communication Practice

* “DNS domain ko IP me resolve karta hai.”
* “DNS issues se application unreachable lag sakta hai.”

---

# SSH & Remote Access

## SSH

### SSH kya hai

Secure remote login protocol.

### Iska use kisliye hota hai

Remote server securely access karne ke liye.

### Ye internally kaise kaam karta hai

Encrypted communication tunnel establish hoti hai.

### Working Steps

SSH request → Authentication → Secure session → Command execution

### Mental Image / Analogy

Secure private tunnel.

### Real Engineer Usage

* Server administration
* Deployments
* Remote debugging

### Common Commands

```bash
ssh user@server-ip
scp file.txt user@server:/tmp
```

### Troubleshooting Thinking

* SSH port open?
* Authentication fail?
* Key permission issue?

### Communication Practice

* “SSH secure encrypted remote access provide karta hai.”
* “Production servers mostly SSH se manage hote hain.”

---

## SSH Keys

### SSH Keys kya hai

Password-less authentication mechanism.

### Iska use kisliye hota hai

Secure login automation ke liye.

### Ye internally kaise kaam karta hai

Public-private key pair verify hota hai.

### Working Steps

Key generate → Public key server pe copy → Authentication verify → Access grant

### Mental Image / Analogy

Lock aur unique key system.

### Real Engineer Usage

* CI/CD automation
* Secure production access
* Git authentication

### Common Commands

```bash
ssh-keygen
ssh-copy-id
```

### Troubleshooting Thinking

* Wrong key?
* Permission 600 missing?
* Authorized_keys issue?

### Communication Practice

* “SSH keys passwords se secure hote hain.”
* “Automation environments me SSH keys commonly use hoti hain.”

---

# Virtualization (VirtualBox/VM)

## Virtual Machine (VM)

### VM kya hai

Ek virtual computer jo real computer ke andar run karta hai.

### Iska use kisliye hota hai

* Testing
* Learning
* Isolation
* Multiple OS run karne ke liye

### Ye internally kaise kaam karta hai

Hypervisor hardware resources share karta hai.

### Working Steps

VM create → CPU/RAM allocate → OS install → Virtual machine run

### Mental Image / Analogy

Ek apartment building me alag rented rooms.

### Real Engineer Usage

* Dev/Test environments
* Sandbox systems
* Lab setup

### Common Tools

* VirtualBox
* VMware
* Hyper-V

### Troubleshooting Thinking

* RAM enough?
* Virtualization enabled?
* Network adapter issue?

### Communication Practice

* “VM isolated environment provide karta hai.”
* “Virtualization resource utilization improve karta hai.”
* “Testing environments ke liye VMs bahut useful hote hain.”

---

## Hypervisor

### Hypervisor kya hai

Software jo VMs manage karta hai.

### Iska use kisliye hota hai

Multiple VMs ko control karne ke liye.

### Ye internally kaise kaam karta hai

Hardware resources virtual machines me divide karta hai.

### Working Steps

Hardware access → Resource allocation → VM isolation → Runtime management

### Mental Image / Analogy

Building manager jo rooms allocate karta hai.

### Real Engineer Usage

* Datacenter virtualization
* Cloud infrastructure
* Resource optimization

### Common Examples

* VirtualBox
* VMware ESXi
* KVM

### Troubleshooting Thinking

* Host overloaded?
* VM freeze?
* Resource contention?

### Communication Practice

* “Hypervisor virtualization ka core component hota hai.”
* “Cloud environments heavily virtualization use karte hain.”
