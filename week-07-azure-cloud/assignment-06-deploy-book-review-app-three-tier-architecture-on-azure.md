# Assignment 6 — Capstone: Deploy Book Review App (Three-Tier Architecture) on Azure

Part of the DevOps Micro Internship (DMI) Cohort 3 with Agentic AI

---

## Purpose

This is the most important assignment of the course. You will deploy the Book Review App in a production-ready, best-practice-compliant three-tier architecture on Azure: separated presentation, application, and database tiers, least-privilege network access, a controlled public entry point, protected secrets, and availability/monitoring evidence.

---

# Task 1 — Design the Azure Three-Tier Architecture

## Goal

Create an architecture diagram and implementation plan identifying the presentation, application, and database components, the chosen Azure services, the public entry point, and the internal traffic paths.

### Evidence

#### Screenshot 1 — Architecture diagram showing the public entry point, three tiers, network boundaries, and traffic flow

![Assignment 5 Screenshots](screenshots/assgn6-img1.png)

---

#### Screenshot 2 — Written architecture assumptions and selected Azure services

![Assignment 5 Screenshots](screenshots/assgn6-img2.png)

---

# Task 2 — Create the Azure Network Foundation

## Goal

Create a dedicated Resource Group and VNet with separate subnets for the web, application, and database tiers, keeping the application and database tiers without direct public access.

### Evidence

#### Screenshot 3 — Resource Group overview showing the assignment resources

![Assignment 5 Screenshots](screenshots/assgn6-img3.png)

---

#### Screenshot 4 — VNet overview showing the address space and all required subnets

![Assignment 5 Screenshots](screenshots/assgn6-img4.png)

---

#### Screenshot 5 — Route-table or Private DNS evidence where applicable

![Assignment 5 Screenshots](screenshots/assgn6-img5.png)

---

# Task 3 — Configure Security and Secret Management

## Goal

Apply least-privilege NSG rules so traffic flows Internet → public entry point → web tier → application tier → database tier, and store credentials in Azure Key Vault or another approved secure mechanism.

### Evidence

#### Screenshot 6 — NSG rules proving least-privilege access between the tiers

![Assignment 5 Screenshots](screenshots/assgn6-img6a.png)

![Assignment 5 Screenshots](screenshots/assgn6-img6b.png)

![Assignment 5 Screenshots](screenshots/assgn6-img6c.png)

---

#### Screenshot 7 — Key Vault or approved secret-management configuration (without displaying secret values)

![Assignment 5 Screenshots](screenshots/assgn6-img7.png)

---

# Task 4 — Deploy the Presentation (Web) Tier

## Goal

Deploy the Book Review App presentation layer on the approved web-tier compute service, configured to route requests to the internal application-tier endpoint, and not directly exposed except through the public entry service.

### Evidence

#### Screenshot 8 — Web-tier compute overview showing subnet and availability configuration

![Assignment 5 Screenshots](screenshots/assgn6-img8.png)

---

#### Screenshot 9 — Terminal or service output proving the presentation layer is running

![Assignment 5 Screenshots](screenshots/assgn6-img9.png)

---

# Task 5 — Deploy the Business (Application) Tier

## Goal

Deploy the Book Review App backend privately in the application subnet, configured to use the private database endpoint and secured environment values, reachable only through its internal endpoint.

### Evidence

#### Screenshot 10 — Application-tier compute overview showing private subnet placement

![Assignment 5 Screenshots](screenshots/assgn6-img10.png)

---

#### Screenshot 11 — Backend process, service, or listening-port evidence

![Assignment 5 Screenshots](screenshots/assgn6-img11.png)

---

#### Screenshot 12 — Internal health-check or API response (without exposing secrets)

![Assignment 5 Screenshots](screenshots/assgn6-img12.png)

---

# Task 6 — Deploy the Managed Database Tier

## Goal

Create a private Azure managed database (public access disabled), with availability/backup/retention settings, the Book Review App schema imported, and access restricted to the application tier only.

### Evidence

#### Screenshot 13 — Database overview showing private connectivity and public access disabled

![Assignment 5 Screenshots](screenshots/assgn6-img13.png)

---

#### Screenshot 14 — Availability, backup, and retention configuration

![Assignment 5 Screenshots](screenshots/assgn6-img14.png)

---

#### Screenshot 15 — Successful schema or connectivity verification (without exposing credentials)

![Assignment 5 Screenshots](screenshots/assgn6-img15.png)

---

# Task 7 — Configure Traffic Management, Availability, and Monitoring

## Goal

Configure the approved public entry service with health probes and backend pools, internal routing for the application tier where required, and enable Azure Monitor/diagnostics/logs/alerts for the key resources.

### Evidence

#### Screenshot 16 — Public entry service showing listener, frontend endpoint, and healthy web targets

![Assignment 5 Screenshots](screenshots/assgn6-img16.png)

---

#### Screenshot 17 — Internal application-tier load-balancing or routing configuration where applicable

![Assignment 5 Screenshots](screenshots/assgn6-img17.png)

---

#### Screenshot 18 — Azure Monitor, diagnostic settings, logs, metrics, or alert evidence

![Assignment 5 Screenshots](screenshots/assgn6-img18.png)

---

# Task 8 — Validate the Production-Style Deployment

## Goal

Confirm the Book Review App works end to end through the public endpoint, with at least one database read and one write, confirm private tiers are not internet-reachable, and complete a safe availability test.

### Evidence

#### Screenshot 19 — Browser showing the Book Review App through the public endpoint

![Assignment 5 Screenshots](screenshots/assgn6-img19a.png)

![Assignment 5 Screenshots](screenshots/assgn6-img19b.png)

---

#### Screenshot 20 — Proof of successful database-backed read and write operations

![Assignment 5 Screenshots](screenshots/assgn6-img20.png)

---

#### Screenshot 21 — Evidence that private tiers are not publicly accessible

![Assignment 5 Screenshots](screenshots/assgn6-img21.png)

---

#### Screenshot 22 — Availability-test and healthy-target evidence

![Assignment 5 Screenshots](screenshots/assgn6-img22.png)

---

#### Public Endpoint

Paste your public endpoint URL here:

http://20.161.151.190

---

### Notes

Summarize what worked, issues encountered and how they were fixed, and the availability/security/secrets/monitoring/backup choices made.

### Project Summary

The Azure three-tier Book Review application was successfully deployed and the major issues encountered during the implementation were ultimately resolved. The deployment included the frontend/web tier, backend/application tier, and Azure Database for MySQL, with the Application Gateway providing the public entry point.

Several troubleshooting issues were encountered, including Nginx configuration conflicts, incorrect API routing, frontend API configuration, Next.js build/chunk errors, backend connectivity, and ensuring that the application servers were correctly connected to the database and load-balancing components. These issues were investigated through Nginx configuration tests, curl/API testing, process and port checks, environment-variable verification, application rebuilds, and backend health checks. After making the necessary corrections, the backend successfully retrieved book records from the Azure MySQL database, and the Application Gateway reported healthy backend targets.

For availability, the architecture used multiple web/application instances and load balancing to provide redundancy and distribute traffic. The Application Gateway was used as the public entry point, while the application and database tiers remained on private network segments.

For security, private tiers were not directly exposed to the Internet. Network security controls were used to restrict access between tiers, while the Application Gateway handled public HTTP traffic. Database access was restricted to the application tier rather than being exposed publicly.

For secrets management, sensitive database credentials were stored using Azure Key Vault rather than being hard-coded into the application configuration. Access to the secrets was controlled through Azure permissions.

For monitoring and operational validation, backend health checks, Application Gateway health status, curl/API tests, Nginx configuration testing, service/process checks, and application logs were used to verify the health and availability of the deployment.

For backup and data protection, Azure Database for MySQL's managed database capabilities and backup features were selected to provide recovery protection for the application's persistent data.

Overall, although the deployment required significant troubleshooting, **I was able to resolve the problems at last and successfully validate the major components of the three-tier architecture.**


---

# Submission Instructions

- Add all required screenshots and links in your submission
- Do not expose passwords, keys, connection strings, or subscription IDs

---

# Completion Checklist

- [ ] Task 1: Architecture diagram and assumptions documented (Screenshots 1–2)
- [ ] Task 2: Network foundation created with isolated tiers (Screenshots 3–5)
- [ ] Task 3: Least-privilege security and secret management configured (Screenshots 6–7)
- [ ] Task 4: Presentation tier deployed (Screenshots 8–9)
- [ ] Task 5: Application tier deployed privately (Screenshots 10–12)
- [ ] Task 6: Managed database tier deployed privately (Screenshots 13–15)
- [ ] Task 7: Public entry, internal routing, and monitoring configured (Screenshots 16–18)
- [ ] Task 8: End-to-end validation and availability test completed (Screenshots 19–22, Public Endpoint, Notes)
- [ ] No sensitive data exposed

---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory) focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.

---

## 📌 Resources

- 🌐 DMI Official Website: https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme  
- 🎓 University: https://university.pravinmishra.com?utm_source=github&utm_medium=readme  
- 💬 Discord Community: https://discord.pravinmishra.com?utm_source=github&utm_medium=readme  
- 📝 Blog: https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme  
- ▶️ YouTube Playlist: https://www.youtube.com/playlist?list=PLFeSNDtI4Cho  
- 🔗 Pravin Mishra (LinkedIn): https://www.linkedin.com/in/pravin-mishra-aws-trainer/  
- 🏢 CloudAdvisory (LinkedIn): https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of DevOps Micro Internship (DMI) Cohort 3 — Agentic AI Track.*
