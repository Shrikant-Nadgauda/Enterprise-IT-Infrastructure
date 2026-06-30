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

