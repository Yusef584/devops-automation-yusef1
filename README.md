DevOps Automation Project – CMP6237  
Author: Yusef Saleh  
Module: DevOps and Enterprise Automation  
University: Birmingham City University  

---

📌 Overview
This project demonstrates a complete DevOps automation pipeline designed for *Evolving Ltd.*, a company modernising its infrastructure by adopting DevOps and Infrastructure as Code (IaC) practices.  

The solution automates the entire workflow:

1. **Infrastructure provisioning** using **Terraform**  
2. **Server configuration** using **Ansible**  
3. **Application containerisation** using **Docker**  
4. **Continuous Integration (CI)** using **GitHub Actions**

Each layer works together to create a fully automated, repeatable, and reliable deployment pipeline.

---

🏗️ Project Architecture

```
Infrastructure (Terraform)
        ↓
Server Configuration (Ansible)
        ↓
Container Build & Deployment (Docker)
        ↓
Automation & Testing (GitHub Actions)
```

This pipeline demonstrates the core DevOps principles: automation, reproducibility, CI/CD, and infrastructure consistency.

---

📁 Repository Structure

```
devops-automation-yusef/
│
├── terraform/            # Infrastructure as Code
│   ├── main.tf
│   ├── provider.tf
│   ├── variables.tf
│   └── outputs.tf
│
├── ansible/              # Server configuration & provisioning
│   ├── site.yml
│   └── inventory
│
├── app/                  # Dockerised application
│   ├── Dockerfile
│   └── app.py (hello world application)
│
└── .github/
    └── workflows/
        └── ci.yml        # CI pipeline for Terraform & Docker
```

---

⚙️ Terraform – Infrastructure as Code
Terraform is used to automatically provision the infrastructure required for the solution.

**Features:**
- Creates a Virtual Machine
- Applies networking & firewall rules
- Declares resources using IaC best practices
- Outputs the server IP for Ansible

Commands Used:
```bash
terraform init
terraform plan
terraform apply
```

---

🛠️ Ansible – Server Configuration Automation
After the VM is deployed, Ansible configures it automatically.

**Key Tasks:**
- Update system packages  
- Install Docker  
- Set up environment for deployment  
- Pull and run Docker containers  

Run Command:
```bash
ansible-playbook -i inventory site.yml
```

---

🐳 Docker – Application Containerisation
The application is packaged into a Docker container to ensure consistent behaviour across environments.

**Docker Features:**
- Lightweight Hello World application  
- Dockerfile defines environment  
- Container runs on the Terraform-provisioned VM  

Commands:
```bash
docker build -t yusef-app .
docker run -d -p 80:80 yusef-app
```

---

🔄 GitHub Actions – Continuous Integration
A CI workflow is implemented to automate validation and testing on every push.

**Workflow Steps:**
- Validate Terraform syntax  
- Build Docker image  
- Run tests (if applicable)  
- Provide automated feedback in pull requests  

Workflow File:
Located in: `.github/workflows/ci.yml`


🔐 Security Considerations
The project follows best-practice security measures:

- SSH key authentication (no passwords)  
- Minimal exposed ports  
- Secrets stored outside source code (no hardcoded credentials)  
- Lightweight, secure Docker images  
- IaC ensures consistent, auditable environments  

---

🧪 Testing & Monitoring
A test plan is included to verify:

- Terraform infrastructure builds successfully  
- Docker images build without errors  
- Application responds to HTTP requests  
- Pipeline logs confirm automation steps are successful  

Monitoring is planned using:
- Logs  
- Status checks  
- CI workflow results  

---

🌱 Sustainability Considerations
- Automated environments reduce energy waste  
- Lightweight Docker images reduce compute load  
- Reusable IaC configurations prevent manual repetition  
- Minimal-resource VM selected for efficiency  

---

🧾 Conclusion
This automated system provides Evolving Ltd. with:

- A fully automated deployment workflow  
- Consistent and reproducible infrastructure environments  
- An efficient and scalable DevOps foundation  
- Improved reliability, security, and resource usage  

This repository demonstrates the entire pipeline required for Checkpoint 2 and forms the basis for the final Viva.

---

📬 Contact
For marking or further clarification:  
**Student: Yusef Saleh**  
**Student No: 22158484**

