Prerequisites
Before you begin, ensure you have the following installed:

Git: Install Git

Docker: Install Docker

Docker Compose: Install Docker Compose


Repository Structure
news-orchestration/
├── docker/                   # Docker configurations for each service
├── docker-compose.yml        # Docker Compose configuration for local development
├── .gitmodules               # Git submodule configurations
├── README.md                 # This file
├── admin-service/            # Submodule for the Admin Service (Laravel)
├── front-admin/              # Submodule for the Front-Admin (React)
└── news-app/                 # Submodule for the News App (React Native/Flutter)


Setting Up the Project
git clone https://github.com/your-username/news-orchestration.git
cd news-orchestration

Initialize and Update Submodules:
git submodule init
git submodule update
