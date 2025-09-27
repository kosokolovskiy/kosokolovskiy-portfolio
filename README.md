# kosokolovskiy-portfolio

Portfolio hub: concise snapshots of each project with links to source code and live demos—Tutor Streamlit (homework & analytics), AWS Terraform IaC, Telegram bots, and more. Clear docs, quickstarts, and architecture notes.

---

## 📑 Contents
- [kosokolovskiy-portfolio](#kosokolovskiy-portfolio)
  - [📑 Contents](#-contents)
    - [Tutor Streamlit for Students](#tutor-streamlit-for-students)
    - [Tutor Working Bot (Telegram)](#tutor-working-bot-telegram)
    - [Hub Infrastructure (AWS + Terraform)](#hub-infrastructure-aws--terraform)
  - [Coming Soon](#coming-soon)

---

### Tutor Streamlit for Students

A **web platform** for assigning homework, tracking progress, and visualizing student stats. RBAC-powered (Admin/Student/Demo) with sections for Homework, Informatics, Mathematics, Variants, and per-student/overall statistics. Optional AI checks/explanations.

**Highlights**
- Role-based menus & permissions (RBAC)
- Assignments + variants, progress tracking, charts
- Admin dashboard: student & topic breakdowns
- Clean Streamlit UI; quick local start with `uv`
- Secrets-safe: `.env.example`, no PII in code

**Tech**
Python 3.11, Streamlit, pandas, matplotlib  
DB: MySQL (RDS) or single-EC2 Mongo option  
AWS: EC2 + Nginx + CloudFront + Route53  
Terraform for IaC

**Links**
- Code: https://github.com/kosokolovskiy/tutor_streamlit_main  
- Docs: https://github.com/kosokolovskiy/tutor_streamlit_main#readme  

---

### Tutor Working Bot (Telegram)

An **extension to the Tutor Streamlit platform** designed for everyday convenience and better service. The bot gives students and tutors a fast, chat-first way to manage homework: real-time reminders, quick status checks, and simple admin actions—without opening the website.

**Highlights**
- Student commands: `/todo`, `/progress`, `/status`
- Admin: `/hw_echo <user>` to refresh cached data
- MySQL for structured data; MongoDB for logs/history
- Query caching to reduce DB load; multi-student support
- CI/CD to EC2 with systemd auto-restart

**How it works**
- Reads secure `creds.ini` at deploy time (never committed)
- Homework/progress in MySQL; logs/diffs/cache events in MongoDB
- Admin can rebuild cache; students read from cache for snappy replies

**Tech**
Python, python-telegram-bot/aiogram, MySQL, MongoDB, GitHub Actions, EC2, systemd

**Links**
- Code: https://github.com/kosokolovskiy/tutor_working_bot/tree/dev  
- Docs: https://github.com/kosokolovskiy/tutor_working_bot/tree/dev#readme  

---

### Hub Infrastructure (AWS + Terraform)

An **imported Terraform project** for managing existing AWS resources of the Hub platform.  
The setup ensures structure, consistency, and best practices—while keeping **all current resources intact** (no recreation).

**Highlights**
- EC2 (Ubuntu 22.04, `t3.nano`) with Elastic IP `3.67.163.253`  
- RDS MySQL (8.0.42, `db.t3.micro`, 20 GB, 7-day backups)  
- S3 buckets: `kosokolovsky-bucket-svgs`, `lambda-layers-kosokolovskiy`  
- Security groups restricted by CloudFront prefix list  
- Imported state from legacy infra—now codified and maintainable

**How it works**
- Uses `terraform import` to bind existing AWS resources  
- Common tags for ownership and environment tracking  
- Separate modules for compute, networking, database, and storage  
- Identical environments: dev / staging / prod  

**Tech**
Terraform, AWS (EC2, RDS, S3, CloudFront, IAM, SGs)  

**Links**
- Code: https://github.com/kosokolovskiy/hub_infrastructure  
- Docs: https://github.com/kosokolovskiy/hub_infrastructure#readme  

---

## Coming Soon

New projects is already ready and links will be added shortly 🚀
