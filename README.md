# AWS Week 05 — Database Services (Amazon RDS & DynamoDB)

![AWS](https://img.shields.io/badge/AWS-RDS%20%7C%20MySQL-orange?logo=amazonaws)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Institute](https://img.shields.io/badge/IT--Simplera-Cloud%20Computing-blue)

## 📌 Overview

This repository contains my Week 05 assignment submission for the **Cloud Computing Internship** at **IT-Simplera Institute**. The assignment focuses on **AWS Database Services**, specifically:

- Deploying a fully managed relational database using **Amazon RDS (MySQL)**
- Connecting to the database using **MySQL Workbench**
- Creating and managing tables using **SQL**
- Understanding **Amazon DynamoDB** as a NoSQL alternative
- Performing **database backup and recovery** using RDS snapshots

## 🎯 Objectives

- Understand the difference between relational (SQL) and non-relational (NoSQL) databases
- Launch and configure an Amazon RDS MySQL instance from the AWS Management Console
- Secure the database using VPC security groups
- Connect remotely via MySQL Workbench
- Perform CRUD-style operations (Create, Insert, Select) using SQL
- Take manual snapshots and review automated backup settings

## 🛠️ Tools & Services Used

| Tool / Service | Purpose |
|---|---|
| **Amazon RDS** | Managed relational database hosting (MySQL engine) |
| **MySQL Workbench** | GUI client to connect and run SQL queries |
| **AWS VPC Security Groups** | Firewall rules controlling database access |
| **Amazon DynamoDB** *(theory)* | NoSQL database comparison |
| **AWS Management Console** | Provisioning and monitoring resources |

## 📂 Repository Contents

```
├── Week05_Database_Services_Report.docx   # Full assignment report with screenshots
└── README.md                              # This file
```

## 🗄️ Database Configuration Summary

| Setting | Value |
|---|---|
| Engine | MySQL 8.4.9 |
| Instance class | db.t4g.micro (Free Tier) |
| Database identifier | `itsimplera-week5-db` |
| Database name | `itsimplera_week5` |
| Master username | `admin` |
| Port | `3306` |
| Public access | Enabled (for Workbench connectivity) |

## 🧱 Table Schema

```sql
CREATE TABLE interns (
    intern_id     INT AUTO_INCREMENT PRIMARY KEY,
    full_name     VARCHAR(100) NOT NULL,
    email         VARCHAR(100) UNIQUE NOT NULL,
    track         VARCHAR(50),
    joined_date   DATE
);
```

## 🔍 Sample Queries Run

```sql
SELECT * FROM interns;
SELECT full_name, track FROM interns WHERE track = 'Cloud Computing';
SELECT COUNT(*) AS total_interns FROM interns;
```

## 💾 Backup & Recovery

- ✅ Manual snapshot created: `itsimplera-week5-manual-snapshot`
- ✅ Automated backups reviewed (daily backup window + retention period)

## 📊 RDS vs DynamoDB — Quick Comparison

| Aspect | Amazon RDS (MySQL) | Amazon DynamoDB |
|---|---|---|
| Data model | Relational (fixed schema) | Key-value / document (flexible schema) |
| Query language | SQL | API-based (GetItem, Query, Scan) |
| Scaling | Vertical + read replicas | Automatic, horizontal |
| Best use case | Structured data with relationships | High-scale, low-latency apps |
| Backup | Automated backups + manual snapshots | Point-in-time recovery + on-demand backups |

## 📖 Key Learnings

- Hands-on experience provisioning a managed relational database on AWS
- Configuring network security (VPC security groups, inbound rules)
- Connecting to a cloud database from a local SQL client
- Practical SQL operations: `CREATE`, `INSERT`, `SELECT`
- Understanding backup strategies for production-grade databases

## 👤 Author

**Jaweria Mushtaq**
Cloud Computing Intern — IT-Simplera Institute
Instructor: Zohaib Ali

---

*This project was completed as part of the Week 05 hands-on assignment for the Cloud Computing Internship program.*
