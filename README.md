# kosokolovskiy-portfolio
Portfolio hub: concise snapshots of each project with links to source code and live demos—Tutor Streamlit (homework &amp; analytics), AWS Terraform IaC, Telegram bots, and more. Clear docs, quickstarts, and architecture notes


### Tutor Streamlit for Students

A web platform for assigning homework, tracking progress, and visualizing student stats. RBAC-powered (Admin/Student/Demo) with sections for Homework, Informatics, Mathematics, Variants, and per-student/overall statistics. Optional AI checks/explanations.

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
