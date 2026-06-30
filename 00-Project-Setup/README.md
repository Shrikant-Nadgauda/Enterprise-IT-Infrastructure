# 🚀 Enterprise IT Infrastructure Knowledge Base

> **Phase 01 : Create Project & Initialize Git Repository**

![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github)
![Platform](https://img.shields.io/badge/Platform-Windows-blue?style=for-the-badge)
![Shell](https://img.shields.io/badge/Shell-Git%20Bash-black?style=for-the-badge)

---

# 📖 Objective

The objective of this phase is to create a professional project structure, initialize a Git repository, and prepare the project for GitHub version control following enterprise standards.

---

# 📋 Prerequisites

- Git Installed
- GitHub Account
- Windows Operating System
- Git Bash

---

# 📂 Target Directory

```text
D:\Enterprise-IT-Infrastructure
```

---

# 🛠 Step 1 — Open D Drive

Open **File Explorer**

Navigate to

```text
D:\
```

---

# 🛠 Step 2 — Create Project Folder

Create a new folder.

```text
Enterprise-IT-Infrastructure
```

---

# 🛠 Step 3 — Open Git Bash

Right Click on the project folder

```
Open Git Bash Here
```

---

# 🛠 Step 4 — Verify Current Directory

```bash
pwd
```

### ✅ Expected Output

```text
/d/Enterprise-IT-Infrastructure
```

---

# 🛠 Step 5 — Verify Folder is Empty

```bash
ls
```

### ✅ Expected Output

```text
(No files)
```

---

# 🛠 Step 6 — Initialize Git Repository

```bash
git init
```

### ✅ Expected Output

```text
Initialized empty Git repository in D:/Enterprise-IT-Infrastructure/.git/
```

---

# 🛠 Step 7 — Rename Default Branch

```bash
git branch -M main
```

---

# 🛠 Step 8 — Verify Repository Status

```bash
git status
```

### ✅ Expected Output

```text
On branch main

No commits yet

nothing to commit
```

---

# 🛠 Step 9 — Create Enterprise Folder Structure

```bash
mkdir 00-Project-Setup 01-Projects 02-HLD 03-LLD 04-Infrastructure-Deep-Dive 05-Security-Review 06-Runbooks 07-Diagrams 08-Scripts 09-Templates 10-Assets
```

---

# 🛠 Step 10 — Verify Folder Structure

```bash
ls
```

### ✅ Expected Output

```text
00-Project-Setup
01-Projects
02-HLD
03-LLD
04-Infrastructure-Deep-Dive
05-Security-Review
06-Runbooks
07-Diagrams
08-Scripts
09-Templates
10-Assets
```

---

# 🛠 Step 11 — Create Root Files

```bash
touch README.md LICENSE CHANGELOG.md .gitignore
```

---

# 🛠 Step 12 — Verify Root Files

```bash
ls
```

### ✅ Expected Output

```text
README.md
LICENSE
CHANGELOG.md
.gitignore
```

---

# 🛠 Step 13 — Create README.md in Every Folder

```bash
for dir in */; do touch "${dir}README.md"; done
```

---

# 🛠 Step 14 — Verify README Files

```bash
find . -name README.md
```

### ✅ Expected Output

```text
./README.md
./00-Project-Setup/README.md
./01-Projects/README.md
./02-HLD/README.md
./03-LLD/README.md
./04-Infrastructure-Deep-Dive/README.md
./05-Security-Review/README.md
./06-Runbooks/README.md
./07-Diagrams/README.md
./08-Scripts/README.md
./09-Templates/README.md
./10-Assets/README.md
```

---

# 🛠 Step 15 — Check Repository Status

```bash
git status
```

### ✅ Expected Output

```text
On branch main

No commits yet

Untracked files:
README.md
LICENSE
CHANGELOG.md
.gitignore
00-Project-Setup/
01-Projects/
02-HLD/
03-LLD/
04-Infrastructure-Deep-Dive/
05-Security-Review/
06-Runbooks/
07-Diagrams/
08-Scripts/
09-Templates/
10-Assets/
```

---

# 🛠 Step 16 — Stage All Files

```bash
git add .
```

---

# 🛠 Step 17 — Verify Staging Area

```bash
git status
```

### ✅ Expected Output

```text
Changes to be committed:
```

---

# 🎯 Phase Summary

In this phase we successfully completed:

- ✅ Created Project Directory
- ✅ Initialized Git Repository
- ✅ Renamed Default Branch to **main**
- ✅ Created Enterprise Folder Structure
- ✅ Created Standard Repository Files
- ✅ Created README for Every Folder
- ✅ Added Files to Git Staging Area

---

# 📁 Repository Structure

```text
Enterprise-IT-Infrastructure
│
├── 00-Project-Setup
├── 01-Projects
├── 02-HLD
├── 03-LLD
├── 04-Infrastructure-Deep-Dive
├── 05-Security-Review
├── 06-Runbooks
├── 07-Diagrams
├── 08-Scripts
├── 09-Templates
├── 10-Assets
│
├── README.md
├── LICENSE
├── CHANGELOG.md
└── .gitignore
```

---

# 🚀 Next Phase

**Phase 02 — First Commit & Push Repository to GitHub**

---

> 💡 **Enterprise Best Practice:** Create small, meaningful commits after every completed milestone instead of one large commit at the end.


# 🚀 Enterprise IT Infrastructure Knowledge Base

> **Phase 02 : First Commit & Push Repository to GitHub**

![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github)
![VS Code](https://img.shields.io/badge/Editor-VS%20Code-007ACC?style=for-the-badge&logo=visualstudiocode)
![Platform](https://img.shields.io/badge/Platform-Windows-blue?style=for-the-badge)

---

# 📖 Objective

In this phase, we will create the first commit, publish the project to GitHub, and establish the standard Git workflow used in enterprise environments.

---

# 📋 Prerequisites

- Phase 01 Completed
- Git Installed
- GitHub Account
- Visual Studio Code Installed
- Internet Connection

---

# 📂 Current Project Directory

```text
D:\Enterprise-IT-Infrastructure
```

---

# 🛠 Step 1 — Open Git Bash

Right Click on the project folder

```text
Open Git Bash Here
```

---

# 🛠 Step 2 — Open Project in Visual Studio Code

```bash
code .
```

### ✅ Expected Output

Visual Studio Code opens with the **Enterprise-IT-Infrastructure** project.

---

# 🛠 Step 3 — Open Project Setup Documentation

Navigate to

```text
00-Project-Setup → README.md
```

Paste the complete **Phase 01** markdown.

Save the file.

Shortcut

```text
Ctrl + S
```

---

# 🛠 Step 4 — Verify Repository Status

```bash
git status
```

### ✅ Expected Output

```text
modified: 00-Project-Setup/README.md
```

---

# 🛠 Step 5 — Stage All Files

```bash
git add .
```

---

# 🛠 Step 6 — Verify Staging Area

```bash
git status
```

### ✅ Expected Output

```text
Changes to be committed:
```

---

# 🛠 Step 7 — Create First Commit

```bash
git commit -m "Initial enterprise repository structure"
```

### ✅ Expected Output

```text
[main (root-commit) xxxxxx]

Initial enterprise repository structure
```

---

# 🛠 Step 8 — Verify Commit History

```bash
git log --oneline
```

### ✅ Expected Output

```text
8f2ab45 Initial enterprise repository structure
```

---

# 🛠 Step 9 — Create GitHub Repository

Open

```text
https://github.com
```

Login using your GitHub account.

---

# 🛠 Step 10 — Create New Repository

Click

```text
New Repository
```

---

# 🛠 Step 11 — Repository Details

Repository Name

```text
Enterprise-IT-Infrastructure
```

Visibility

```text
Public
```

---

# 🛠 Step 12 — IMPORTANT

Keep these options **Unchecked**

```text
☐ Add README

☐ Add .gitignore

☐ Choose License
```

> These files already exist in the local repository.

---

# 🛠 Step 13 — Create Repository

Click

```text
Create Repository
```

GitHub will display repository commands.

---

# 🛠 Step 14 — Connect Local Repository to GitHub

```bash
git remote add origin https://github.com/Shrikant-Nadgauda/Enterprise-IT-Infrastructure.git
```

---

# 🛠 Step 15 — Verify Remote Repository

```bash
git remote -v
```

### ✅ Expected Output

```text
origin  https://github.com/Shrikant-Nadgauda/Enterprise-IT-Infrastructure.git (fetch)

origin  https://github.com/Shrikant-Nadgauda/Enterprise-IT-Infrastructure.git (push)
```

---

# 🛠 Step 16 — Push Repository to GitHub

```bash
git push -u origin main
```

### ✅ Expected Output

```text
Branch 'main' set up to track remote branch 'main' from 'origin'.

Everything up-to-date
```

or during the first push

```text
Enumerating objects...

Counting objects...

Writing objects...

Branch 'main' set up to track 'origin/main'
```

---

# 🛠 Step 17 — Verify Repository on GitHub

Open

```text
https://github.com/Shrikant-Nadgauda/Enterprise-IT-Infrastructure
```

Verify

- ✅ Repository Created
- ✅ Folder Structure Visible
- ✅ README Files Uploaded
- ✅ Project Successfully Published

---

# 💼 Daily Professional Git Workflow

Whenever you complete a task:

### Check Repository Status

```bash
git status
```

---

### Stage Changes

```bash
git add .
```

---

### Create Meaningful Commit

```bash
git commit -m "Added Active Directory documentation"
```

---

### Push Changes

```bash
git push
```

---

# 💡 Enterprise Commit Naming Examples

```bash
git commit -m "Added project folder structure"

git commit -m "Completed Active Directory documentation"

git commit -m "Added FortiGate architecture"

git commit -m "Completed Entra ID security review"

git commit -m "Added Microsoft Intune checklist"

git commit -m "Updated project diagrams"

git commit -m "Improved documentation formatting"
```

---

# 🚀 Enterprise Git Workflow

```text
Modify Files
      │
      ▼
git status
      │
      ▼
git add .
      │
      ▼
git commit -m "Meaningful Message"
      │
      ▼
git push
      │
      ▼
GitHub Repository Updated
```

---

# 🎯 Phase Summary

In this phase we successfully completed:

- ✅ Opened Project in Visual Studio Code
- ✅ Added Phase 01 Documentation
- ✅ Created First Git Commit
- ✅ Verified Commit History
- ✅ Created GitHub Repository
- ✅ Connected Local Repository to GitHub
- ✅ Published Repository
- ✅ Learned Professional Git Workflow

---

# 📌 Best Practices

- Commit frequently.
- Use meaningful commit messages.
- Push changes regularly.
- Keep documentation updated.
- Never commit sensitive information.
- Review changes before every commit.

---

# 🚀 Next Phase

**Phase 03 — Branching Strategy, Feature Development & Pull Requests**

---

> 💡 **Enterprise Best Practice:** Treat GitHub as your engineering diary. Every meaningful improvement should be committed with a clear message, making your learning journey and project history easy to follow and review.

# 🚀 Enterprise IT Infrastructure Knowledge Base

> **Phase 03 : Build Enterprise Repository Structure**

![GitHub](https://img.shields.io/badge/GitHub-Knowledge%20Base-181717?style=for-the-badge&logo=github)
![Documentation](https://img.shields.io/badge/Documentation-Enterprise-blue?style=for-the-badge)
![Project](https://img.shields.io/badge/Project-Infrastructure-green?style=for-the-badge)

---

# 📖 Objective

In this phase, we will create the complete repository structure for documenting an enterprise production infrastructure.

The repository is designed to serve as a long-term knowledge base covering architecture, implementation, operations, security reviews, troubleshooting, and real-world production practices.

---

# 📂 Repository Structure

```text
Enterprise-IT-Infrastructure
│
├── 00-Project-Setup
│
├── 01-Projects
│     └── RK-Project-Details
│
├── 02-HLD
│     └── RK-HLD
│
├── 03-LLD
│     └── RK-LLD
│
├── 04-Infrastructure-Deep-Dive
│
├── 05-Security-Review
│
├── 06-Runbooks
│
├── 07-Diagrams
│
├── 08-Scripts
│
├── 09-Templates
│
├── 10-Assets
│
├── README.md
├── LICENSE
├── CHANGELOG.md
└── .gitignore
```

---

# 📁 Folder Purpose

| Folder | Description |
|---------|-------------|
| 00-Project-Setup | Repository creation and setup documentation |
| 01-Projects | Customer project documentation |
| 02-HLD | High Level Design documents |
| 03-LLD | Low Level Design documents |
| 04-Infrastructure-Deep-Dive | Detailed explanation of every infrastructure component |
| 05-Security-Review | Security review checklists, evidence and reports |
| 06-Runbooks | Operational procedures and SOPs |
| 07-Diagrams | Draw.io, PDF and PNG diagrams |
| 08-Scripts | PowerShell, Bash and CLI scripts |
| 09-Templates | Reusable templates |
| 10-Assets | Images, Icons and supporting files |

---

# 📁 Project Structure

```text
01-Projects
└── RK-Project-Details
```

Contents

```text
README.md
RK-Architecture.drawio
RK-Architecture.pdf
RK-Network-Flow.md
RK-Server-Inventory.xlsx
RK-IP-Addressing.xlsx
RK-Meeting-Notes.md
RK-Project-Timeline.md
```

---

# 📁 High Level Design

```text
02-HLD
└── RK-HLD
```

Contents

```text
README.md
Architecture
Network
Servers
Cloud
Security
Inventory
```

---

# 📁 Low Level Design

```text
03-LLD
└── RK-LLD
```

Contents

```text
README.md
Network
Firewall
Servers
Cloud
VPN
Authentication
```

---

# 📁 Infrastructure Deep Dive

```text
04-Infrastructure-Deep-Dive
```

Enterprise Components

```text
RK-DC-FortiGate-120G
RK-DC-Active-Directory
RK-DC-Certificate-Authority
RK-DC-WSUS
RK-DC-NTP
RK-DC-Backup
RK-DC-Email-Protector
RK-DC-NMS
RK-DC-File-Server
RK-DC-Application-Server
RK-DC-Database-Server

RK-Cloud-Entra-ID
RK-Cloud-Microsoft365
RK-Cloud-Intune
RK-Cloud-Authenticator
```

---

# 📁 Security Review

```text
05-Security-Review
```

Contents

```text
Checklists
Evidence
Reports
```

---

# 📁 Runbooks

```text
06-Runbooks
```

Contents

```text
New User
Password Reset
VPN Access
Certificate Renewal
Laptop Build
```

---

# 📁 Diagrams

```text
07-Diagrams
```

Contents

```text
DrawIO
PNG
PDF
```

---

# 📁 Scripts

```text
08-Scripts
```

Contents

```text
PowerShell
Bash
FortiGate CLI
```

---

# 📁 Templates

```text
09-Templates
```

Contents

```text
Checklist
Evidence
Email
HLD
LLD
```

---

# 📁 Assets

```text
10-Assets
```

Contents

```text
Images
Icons
Logos
```

---

# 🎯 Phase Summary

Repository foundation is now complete.

The next phases will focus entirely on documenting the production infrastructure component by component.

---

> **Repository Status:** ✅ Repository Structure Completed

# 🚀 Enterprise IT Infrastructure Knowledge Base

> **Phase 04 : Create Enterprise Repository Structure**

![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Enterprise%20Repository-181717?style=for-the-badge&logo=github)
![Documentation](https://img.shields.io/badge/Documentation-Professional-blue?style=for-the-badge)

---

# 📖 Objective

Create the complete enterprise repository structure using the minimum number of Git Bash commands following professional engineering practices.

---

# 📂 Target Repository

```text
Enterprise-IT-Infrastructure
```

---

# 🛠 Step 1 — Open Project

```bash
cd /d/Enterprise-IT-Infrastructure
```

**Purpose:** Navigate to the project directory.

---

# 🛠 Step 2 — Open Visual Studio Code

```bash
code .
```

**Purpose:** Open the project in Visual Studio Code.

---

# 🛠 Step 3 — Create Project Directories

```bash
mkdir -p \
01-Projects/RK-Project-Details \
02-HLD/RK-HLD/{Architecture,Network,Servers,Cloud,Security,Inventory} \
03-LLD/RK-LLD/{Network,Firewall,Servers,Cloud,VPN,Authentication} \
04-Infrastructure-Deep-Dive/{RK-DC-FortiGate-120G,RK-DC-Active-Directory,RK-DC-Certificate-Authority,RK-DC-WSUS,RK-DC-NTP,RK-DC-Backup,RK-DC-Email-Protector,RK-DC-NMS,RK-DC-File-Server,RK-DC-Application-Server,RK-DC-Database-Server,RK-Cloud-Entra-ID,RK-Cloud-Microsoft365,RK-Cloud-Intune,RK-Cloud-Authenticator} \
05-Security-Review/{Checklists,Evidence,Reports} \
06-Runbooks/{New-User,Password-Reset,VPN-Access,Certificate-Renewal,Laptop-Build} \
07-Diagrams/{DrawIO,PNG,PDF} \
08-Scripts/{PowerShell,Bash,FortiGate-CLI} \
09-Templates/{Checklist,Evidence,Email,HLD,LLD} \
10-Assets/{Images,Icons,Logos}
```

**Purpose:** Create the complete enterprise folder hierarchy.

---

# 🛠 Step 4 — Create README Files

```bash
find . -type d -exec touch {}/README.md \;
```

**Purpose:** Create a README.md inside every directory.

---

# 🛠 Step 5 — Create Project Files

```bash
touch \
01-Projects/RK-Project-Details/RK-Architecture.drawio \
01-Projects/RK-Project-Details/RK-Architecture.pdf \
01-Projects/RK-Project-Details/RK-Network-Flow.md \
01-Projects/RK-Project-Details/RK-Server-Inventory.xlsx \
01-Projects/RK-Project-Details/RK-IP-Addressing.xlsx \
01-Projects/RK-Project-Details/RK-Meeting-Notes.md \
01-Projects/RK-Project-Details/RK-Project-Timeline.md
```

**Purpose:** Create the initial project documentation files.

---

# 🛠 Step 6 — Verify Repository Structure

```bash
tree -L 3
```

**Purpose:** Display the repository structure.

---

# 🛠 Step 7 — Verify Repository Status

```bash
git status
```

**Purpose:** Display newly created files.

---

# 🛠 Step 8 — Stage All Files

```bash
git add .
```

**Purpose:** Add all files to the staging area.

---

# 🛠 Step 9 — Commit Changes

```bash
git commit -m "Add enterprise repository folder structure and project templates"
```

**Purpose:** Save the repository structure.

---

# 🛠 Step 10 — Push to GitHub

```bash
git push
```

**Purpose:** Upload the latest changes to GitHub.

---

# 🎯 Phase Summary

In this phase we successfully created:

- ✅ Enterprise Project Structure
- ✅ HLD Framework
- ✅ LLD Framework
- ✅ Infrastructure Deep Dive Framework
- ✅ Security Review Framework
- ✅ Runbook Framework
- ✅ Diagram Framework
- ✅ Script Framework
- ✅ Template Framework
- ✅ Asset Framework

---

# 📁 Repository Preview

```text
Enterprise-IT-Infrastructure
│
├── 00-Project-Setup
├── 01-Projects
├── 02-HLD
├── 03-LLD
├── 04-Infrastructure-Deep-Dive
├── 05-Security-Review
├── 06-Runbooks
├── 07-Diagrams
├── 08-Scripts
├── 09-Templates
├── 10-Assets
│
├── README.md
├── LICENSE
├── CHANGELOG.md
└── .gitignore
```

---

# 🚀 Enterprise IT Infrastructure Knowledge Base

> **Phase 05 : Create Project Documentation Structure**

![Git](https://img.shields.io/badge/Git-Git%20Bash-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Documentation-181717?style=for-the-badge&logo=github)
![Project](https://img.shields.io/badge/Project-Enterprise-blue?style=for-the-badge)

---

# 📖 Objective

Create the project documentation directory and all standard Markdown files required for documenting an enterprise infrastructure project.

---

# 🛠 Step 1 — Navigate to Project Repository

```bash
cd /d/Enterprise-IT-Infrastructure
```

**Purpose:** Open the project repository.

---

# 🛠 Step 2 — Create Project Directory

```bash
mkdir -p 01-Projects/RK-Project-Details
```

**Purpose:** Create the customer project folder.

---

# 🛠 Step 3 — Create Documentation Files

```bash
touch \
01-Projects/README.md \
01-Projects/RK-Project-Details/README.md \
01-Projects/RK-Project-Details/{01-Project-Overview,02-Customer-Environment,03-Site-Information,04-Network-Overview,05-Server-Inventory,06-Cloud-Services,07-Branch-Connectivity,08-Technology-Stack,09-Architecture,10-Scope}.md
```

**Purpose:** Create all project documentation files using a single command.

---

# 🛠 Step 4 — Verify Structure

```bash
tree 01-Projects
```

### ✅ Expected Output

```text
01-Projects
│
├── README.md
│
└── RK-Project-Details
    │
    ├── README.md
    ├── 01-Project-Overview.md
    ├── 02-Customer-Environment.md
    ├── 03-Site-Information.md
    ├── 04-Network-Overview.md
    ├── 05-Server-Inventory.md
    ├── 06-Cloud-Services.md
    ├── 07-Branch-Connectivity.md
    ├── 08-Technology-Stack.md
    ├── 09-Architecture.md
    └── 10-Scope.md
```

---

# 🛠 Step 5 — Save Changes

```bash
git add .
git commit -m "Create enterprise project documentation structure"
git push
```

---

# 🎯 Phase Summary

✅ Project directory created

✅ Documentation framework created

✅ Standard Markdown files created

✅ Repository updated on GitHub

---

# 🚀 Next Phase

**Start writing the actual project documentation beginning with:**

```text
01-Projects
└── RK-Project-Details
    └── 01-Project-Overview.md
```

> 📌 **Best Practice:** Create the complete documentation structure first, then start filling each document one by one.
