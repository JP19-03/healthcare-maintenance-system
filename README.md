# BioMedCare - Healthcare Maintenance & Equipment Tracking System 🏥⚡

An end-to-end full-stack medical equipment breakdown tracking, work order management, and operational analytics system.

![Tech Stack](https://img.shields.io/badge/Stack-Java%2017%20%7C%20Spring%20Boot%204%20%7C%20React%2019%20%7C%20PostgreSQL-teal)
![License](https://img.shields.io/badge/License-MIT-blue)

---

## 💻 Dev

1. Clone the repository.
2. Create an `.env` file based on the `.env.template` file and set the necessary environment variables:
   ```bash
   cp .env.template .env
   ```
3. Run `docker compose up --build` to start the application.

---

## 🛠️ Steps to Create & Work with Git Submodules

### Cloning a Repository with Submodules
When someone clones the repository for the first time, they must run the following command to initialize and update the sub-modules:
```bash
git clone <repository_url>
cd <repository_name>
git submodule update --init --recursive
```

### Adding a New Submodule
Add the submodule, where `repository_url` is the URL of the repository and `directory_name` is the name of the folder where you want to save the sub-module (it must not already exist in the project):
```bash
git submodule add <repository_url> <directory_name>
```

Add the changes to the main repository (`git add`, `git commit`, `git push`). Example:
```bash
git add .
git commit -m "Add submodule"
git push
```

### Updating Submodules
To update the sub-module references to the latest remote commit:
```bash
git submodule update --remote
```

### ⚠️ Important Rules for Submodules
> [!IMPORTANT]
> When working in the repository that contains sub-modules, **first update and push in the sub-module and then in the main repository.**
>
> If you do it the other way around, you will lose the sub-module references in the main repository and will have to resolve conflicts.

---

## 🌟 Key Highlights & Features

- **Full-Stack Architecture**: Spring Boot 4 Java 17 REST API + React 19 TypeScript Frontend.
- **Domain-Driven Design (DDD)**: Clean Bounded Contexts (`iam`, `inventory`, `maintenance`, `analytics`).
- **Role-Based Access Control (RBAC)**: Distinct workflows for Administrators (`ROLE_ADMIN`), Department Heads (`ROLE_MANAGER`), and Biomedical Technicians (`ROLE_TECH`).
- **Real-Time Analytics Dashboard**: Live metrics for Hospital Operational Readiness Rate (%), Mean Time to Resolution (MTTR), Department Machinery Density, and Technician Repair Workloads.
- **Mobile-First UX**: Responsive off-canvas sidebar drawer, mobile header navigation, and scrollable table wrappers.

---

## 🌐 Access Ports & Services

* 🎨 **Frontend Application**: [http://localhost:5173](http://localhost:5173)
* ⚙️ **Backend REST API**: [http://localhost:8080/api/v1](http://localhost:8080/api/v1)
* 📑 **OpenAPI / Swagger UI Docs**: [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)
* 🗄️ **PostgreSQL Database**: `localhost:5432` (Database: `healthcare_db`)

---

## 👥 Demo User Credentials

The database initializes with seed users for testing each system role:

| Role | Username | Password | Access Rights |
| :--- | :--- | :--- | :--- |
| **`ROLE_ADMIN`** | `johan` | `password123` | Full administrative access (Users directory, Equipment, Work Orders, Analytics). |
| **`ROLE_MANAGER`** | `manager1` | `password123` | Equipment management, Ticket creation, Technician assignment, Analytics. |
| **`ROLE_TECH`** | `carlos_tech` | `password123` | Personal work queue (`/my-queue`), Technical resolution, Read-only equipment view. |

---

## 📚 Submodule Documentation Links

* 📄 [Backend Documentation (`backend/README.md`)](./backend/README.md)
* 🎨 [Frontend Documentation (`frontend/README.md`)](./frontend/README.md)
