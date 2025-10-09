# 📰 News Orchestrator

The **News Orchestrator** repository manages the orchestration of the **News Platform**, which consists of multiple submodules — one for the backend and one for the frontend.  
This repository is designed to centralize and synchronize the development of all services related to the project.

---

## 📁 Project Structure



news-orchestrator/
│
├── backend-news-service/ # Backend API service
├── frontend-news-service/ # Frontend application
└── ...

Each service is included as a **Git submodule**, allowing independent version control while keeping the orchestration centralized.

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/news-orchestrator.git
cd news-orchestrator

2. Initialize Submodules

There are two ways to initialize the submodules, depending on what you need:

✅ Initialize all submodules:
git submodule update --init

⚙️ Initialize a specific submodule (for example, the backend):
git submodule update --init backend-news-service

3. Enter the Service Folder

After initializing the desired service, navigate into it:

cd backend-news-service

🧩 Useful Commands
Description	Command
Update submodules to the latest commit	git submodule update --remote
Pull changes for all submodules	git submodule foreach git pull origin master
Add a new submodule	git submodule add <repo-url> <folder-name>
Remove a submodule	git submodule deinit <folder-name> && rm -rf .git/modules/<folder-name> && git rm -f <folder-name>

🧑‍💻 Author

Paulo Roberto
Full-Stack Developer — GitHub Profile


