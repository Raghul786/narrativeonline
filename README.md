Reddit style web application 
🧭 Project Overview

This project demonstrates an end-to-end enterprise application setup using Oracle WebLogic Server and Oracle Database, focusing on infrastructure, middleware, and runtime integration, not application development.

The goal is to simulate a real-world banking / enterprise environment where:

Infrastructure teams manage WebLogic & DB

Applications are deployed as compiled artifacts

Load balancing, networking, and security are first-class concerns

🏗️ Architecture

Client / Browser
      |
      | HTTP
      v
HAProxy (on-prem)
      |
      v
Apache Web Server (optional)
      |
      v
WebLogic Managed Server
      |
      | JNDI (jdbc/RedditDS)
      v
Oracle Database XE 21c (XEPDB1)


⚙️ Technology Stack

OS: CentOS 9 / Oracle Linux 8

Middleware: Oracle WebLogic Server 14c

Database: Oracle XE 21c (Multitenant – XEPDB1)

Web: Apache HTTPD, HAProxy

DB Connectivity: WebLogic JDBC DataSource (JNDI)

Networking: On-prem NAT + Host-Only (VMware)

Tools: SQL*Plus, SQL Developer, VS Code


🗄️ Database Design
Users

reddit_app – schema owner

reddit_run – runtime user (least privilege)

Objects

Users table

Posts table

Comments table

Primary keys, foreign keys, indexes

Referential integrity enforced

Includes RCA for common Oracle errors such as
ORA-02291: integrity constraint violated


🚀 Application Deployment

WAR deployed on WebLogic Managed Server

JDBC DataSource configured and tested from console

End-to-end DB call validated from application

Focus on:

Deployment lifecycle

Staging directories

Admin vs Managed Server behavior

Clean redeploy strategy

🔍 What This Project Emphasizes

✅ Enterprise-style WebLogic deployment
✅ Real Oracle DB integration
✅ Infra-first mindset (not framework-driven)
✅ Troubleshooting & RCA
✅ Production-relevant patterns

📈 Possible Extensions

WebLogic Cluster

HAProxy → WebLogic SSL termination

WAF integration

AWR / performance tuning

CI/CD for WAR delivery
