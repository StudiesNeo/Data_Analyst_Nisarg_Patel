# Data_Analyst_Nisarg_Patel
# 🎓 UCW Academic Department AWS Cloud Management

  This project builds a serverless, end‑to‑end AWS pipeline for UCWA’s academic department to analyze workload distribution. I ingest CSV into S3, profile and clean the data via Glue DataBrew, transform and enrich it using Glue ETL and crawlers, then catalogue and query it in Athena. The result is a scalable, maintainable analytics workflow that provides timely insights for academic planning and resourcing.
---

## 1. Project Overview

- **Title:** Perform descriptive analysis to optimize faculty workload and streamline the process.   
- **Scope:** Design and implement secure landing zones and perform the analytical operations for UCW’s Academic department and Analytics workflows  

---

## 2. Objectives

1. **Landing Zone Design**  
   - Build isolated AWS accounts/environments (Dev vs Prod) using **AWS Control Tower** and **Organizations** for centralized governance :contentReference[oaicite:1]{index=1}  
2. **Security & Compliance**  
   - Apply Service Control Policies (SCPs), segregated IAM roles, AWS Security Hub, and CloudTrail for visibility and enforcement :contentReference[oaicite:2]{index=2}  
3. **Registrar Office High Availability**  
   - Deploy two EC2 web servers (IIS on Windows) in multi-AZ subnets, with hosting for “Registrar’s Office” website and backup automation  
4. **Academic Data Analytics Environment**  
   - Build ETL pipelines for operational data (.CSV from Course_Evaluation), storing results in S3 and analyzing via AWS Lambda, Athena, or Amazon RDS  
5. **Governance, Cost & Monitoring**  
   - Enable AWS Cost Explorer, generate billing alerts, and compile metrics dashboards in Amazon CloudWatch / QuickSight  

---

## 3. Methodology

### Phase A – **Assess & Plan**
- Conducted readiness assessments using **AWS Cloud Adoption Framework** (CAF) focusing on Business, People, and Governance :contentReference[oaicite:3]{index=3}  
- Identified key migrations: Registrar's web app with high availability and the academic analytics pipeline  

### Phase B – **Landing Zone Implementation**
- Configured **AWS Control Tower** to orchestrate AWS Organizations with two Organizational Units (OUs): _Dev_ and _Prod_  
- Applied SCPs to restrict production resources, enforce encryption, and limit public access  

### Phase C – **Web App Migration**
- Provisioned EC2 instances in separate AZs under Prod OU  
- Installed IIS on Windows, deployed Registrar’s web portal, configured ELB for HA and failover  
- Scheduled AMI backups and automated snapshot lifecycle policies  

### Phase D – **Analytics Pipeline**
- Set up S3 buckets for raw and processed data (no public access)  
- Deployed AWS Lambda & Glue jobs to parse CSV, transform data, and load into Athena tables  
- Enabled encryption using AWS KMS customer-managed keys (CMKs) for data at rest  

### Phase E – **Governance & Monitoring**
- Enabled **AWS Security Hub**, **IAM Identity Center**, **Config**, **GuardDuty**, and **CloudTrail**  
- Centralized logs and metrics via **CloudWatch dashboards**  
- Enabled **Cost Explorer** & configured budget alerts  

---

## 4. Architecture Diagram

![Architecture Diagram](docs/architecture-diagram.png)
*Illustrates OUs, networking, web and data pipelines in Dev & Prod environments.*

---

## 5. Tools & Technologies

- **Infrastructure as Code**: AWS Control Tower, CloudFormation, AWS CLI  
- **Compute & Storage**: EC2 (Windows/IIS), Elastic Load Balancer, S3  
- **ETL & Analytics**: AWS Lambda, AWS Glue, Athena  
- **Governance & Security**: Organizations, SCPs, IAM Identity Center, Security Hub, KMS, Config, CloudTrail  
- **Monitoring & Cost**: CloudWatch, Cost Explorer, Budgets  

---

## 6. Deliverables

- **IaC Templates**: Control Tower configuration & CloudFormation scripts under `infrastructure/`  
- **Automated Deployment**: CI/CD pipeline (GitHub Actions) under `.github/workflows/ci-cd.yml`  
- **Analysis Pipeline Code**: Python Lambda/Glue scripts under `src/etl/`  
- **Dashboards**: CloudWatch, Athena queries, QuickSight

