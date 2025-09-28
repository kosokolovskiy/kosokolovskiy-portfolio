# 🌐 kosokolovskiy-portfolio

Welcome to my **personal portfolio hub** 🎯  
Here I collect concise snapshots of my projects—ranging from **Databricks pipelines and dbt models** to **Streamlit apps, Telegram bots, and Terraform infrastructure**.  

Each project comes with:
- 📂 clear docs  
- ⚡ quickstart guides  
- 🏗️ architecture notes  
- 🔗 direct links to code and demos  

💡 Current focus: **Databricks, Machine Learning, and Infrastructure-as-Code (IaC)** for scalable, production-ready data platforms.

---

## 📑 Contents
- [🌐 kosokolovskiy-portfolio](#-kosokolovskiy-portfolio)
  - [📑 Contents](#-contents)
  - [🧑‍💻 Databricks Projects](#-databricks-projects)
    - [Ad Analytics ETL Pipeline](#ad-analytics-etl-pipeline)
  - [🌐 General Projects](#-general-projects)
    - [Tutor Streamlit for Students](#tutor-streamlit-for-students)
    - [Tutor Working Bot (Telegram)](#tutor-working-bot-telegram)
    - [Hub Infrastructure (AWS + Terraform)](#hub-infrastructure-aws--terraform)
  - [🚀 Coming Soon](#-coming-soon)

---

## 🧑‍💻 Databricks Projects

### Ad Analytics ETL Pipeline

A **modern ETL pipeline** for advertising and marketing analytics data, demonstrating enterprise-grade data engineering practices.  
Built on **dbt**, **Databricks Lakehouse**, and **Apache Spark**, it processes raw ad platform data into curated facts, dimensions, and marts.

**Highlights**
- Incremental delta processing for large datasets  
- Fact & dimension modeling with dbt  
- Data quality & freshness tests  
- Automated error handling with AI-powered logic  
- Deployment-ready with Databricks asset bundles  

**Tech**  
Python 3.12, dbt 1.10+, Apache Spark, Databricks, Unity Catalog, GitHub Actions  

**Links**  
- Code: https://github.com/kosokolovskiy/etl_dbt_databricks_marketing  
- Docs: https://github.com/kosokolovskiy/etl_dbt_databricks_marketing#readme  

---

## 🌐 General Projects

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
- Code: https://github.com/kosokolovskiy/tutor_streamlit_IaC  
- Docs: https://github.com/kosokolovskiy/tutor_streamlit_IaC#readme  

---

## 🚀 Coming Soon

New projects are already ready and links will be added shortly 🚀
