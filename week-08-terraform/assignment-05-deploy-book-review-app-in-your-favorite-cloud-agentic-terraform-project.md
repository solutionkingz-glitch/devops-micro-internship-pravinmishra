# Capstone Assignment — Deploy the Book Review App Using Terraform and Claude Code Agentic AI

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Student Details

**Full Name:** Kingsley Erhatiemwonmon  
**Cloud Platform:** AWS  
**GitHub Repository URL:** https://github.com/solutionkingz-glitch/devops-micro-internship-pravinmishra.git
**Public Application URL / Load-Balancer DNS:** http://public-web-alb-219662638.us-east-1.elb.amazonaws.com

---

## Purpose

Deploy the Book Review App using Terraform on AWS or Azure in a secure, highly available, production-style three-tier architecture. Use Claude Code, specialized subagents, Terraform MCP, and validation hooks to support the engineering workflow while keeping all infrastructure-changing operations under human control.

---

# Task 0 — Prepare the Project and Agentic AI Environment

## Goal

Prepare the Book Review App project and configure the provided Claude Code Agentic AI starter kit with project context, specialized subagents, Terraform MCP, validation hooks, and safety guardrails.

## Evidence

### Screenshot 1 — Project `CLAUDE.md`

Add a screenshot of the project `CLAUDE.md` showing the three-tier architecture, security boundaries, Terraform requirements, and human-approval rules.

![Assignment 5 Screenshots](screenshots/assgn5-img1a.png)

![Assignment 5 Screenshots](screenshots/assgn5-img1b.png)

---

### Screenshot 2 — Terraform Engineer Subagent

Add a screenshot showing the Terraform Engineer subagent configuration.

![Assignment 5 Screenshots](screenshots/assgn5-img2.png)

---

### Screenshot 3 — Architecture and Security Reviewer Subagent

Add a screenshot showing the Architecture and Security Reviewer subagent configuration.

![Assignment 5 Screenshots](screenshots/assgn5-img3.png)

---

### Screenshot 4 — Terraform MCP Connection

Add a screenshot showing Terraform MCP connected and available.

![Assignment 5 Screenshots](screenshots/assgn5-img4.png)

---

### Screenshot 5 — Validation Hooks

Add a screenshot showing the configured Claude Code validation hooks.

![Assignment 5 Screenshots](screenshots/assgn5-img5.png)

---

# Task 1 — Design the Three-Tier Architecture

## Goal

Design the required secure, highly available three-tier architecture and create an architecture diagram before building the infrastructure.

The diagram must show:

- VPC or VNet
- Availability Zones or equivalent availability locations
- Six subnets
- Internet connectivity
- NAT or outbound design
- Public load balancer
- Web Tier
- Internal load balancer
- Application Tier
- Managed MySQL
- Read replica
- Main traffic flow

## Architecture Diagram

![Assignment 5 Screenshots](screenshots/assgn5-img5a.png)

---

# Task 2 — Build the Terraform Networking and Security Layers

## Goal

Create the modular Terraform project and implement the network and security layers across the required public and private subnets.

## Evidence

### Screenshot 6 — Modular Terraform Project Structure

Add a screenshot showing the modular Terraform project structure.

![Assignment 5 Screenshots](screenshots/assgn5-img6.png)

---

### Screenshot 7 — Six-Subnet Architecture

Add a screenshot showing the six-subnet architecture across two availability locations.

![Assignment 5 Screenshots](screenshots/assgn5-img7.png)

---

### Screenshot 8 — Public and Private Tier Separation

Add a screenshot showing the public and private tier separation, including routing and security boundaries.

![Assignment 5 Screenshots](screenshots/assgn5-img8a.png)

![Assignment 5 Screenshots](screenshots/assgn5-img8b.png)

---

# Task 3 — Build the Load-Balancing and Compute Layers

## Goal

Deploy the public and internal load balancers and the Web and Application compute resources required by the Book Review App.

## Evidence

### Screenshot 9 — Web and Application Compute

Add a screenshot showing the Web and Application compute resources in their required subnets.

![Assignment 5 Screenshots](screenshots/assgn5-img9.png)

---

### Screenshot 10 — Public Load Balancer

Add a screenshot showing the internet-facing public load balancer.

![Assignment 5 Screenshots](screenshots/assgn5-img10.png)

---

### Screenshot 11 — Internal Load Balancer

Add a screenshot showing the private internal load balancer.

![Assignment 5 Screenshots](screenshots/assgn5-img11.png)

---

### Screenshot 12 — Healthy Targets

Add a screenshot showing healthy target groups or backend pools.

![Assignment 5 Screenshots](screenshots/assgn5-img12.png)

---

# Task 4 — Build the Managed MySQL Database Layer

## Goal

Deploy a private, highly available managed MySQL database with a read replica and restrict database connectivity to the Application Tier.

## Evidence

### Screenshot 13 — Managed MySQL Database

Add a screenshot showing the managed MySQL database deployment.

![Assignment 5 Screenshots](screenshots/assgn5-img13.png)

---

### Screenshot 14 — High Availability

Add a screenshot showing the Multi-AZ or high-availability configuration.

![Assignment 5 Screenshots](screenshots/assgn5-img14.png)

---

### Screenshot 15 — Read Replica

Add a screenshot showing the read replica configuration.

![Assignment 5 Screenshots](screenshots/assgn5-img15.png)

---

### Screenshot 16 — Private Database Access

Add a screenshot showing that the database is private and accepts MySQL traffic only from the Application Tier.

![Assignment 5 Screenshots](screenshots/assgn5-img16.png)

---

# Task 5 — Validate, Review, and Apply the Terraform Configuration

## Goal

Validate the Terraform configuration, review the execution plan using both Agentic AI and human judgment, and apply the infrastructure changes only after all required checks pass.

## Evidence

### Screenshot 17 — Terraform Validation

Add a screenshot showing successful `terraform validate` output.

![Assignment 5 Screenshots](screenshots/assgn5-img17.png)

---

### Screenshot 18 — Terraform Plan

Add a screenshot showing the Terraform plan output.

![Assignment 5 Screenshots](screenshots/assgn5-img18.png)

---

### Screenshot 19 — Terraform Apply

Add a screenshot showing successful `terraform apply` completion.

![Assignment 5 Screenshots](screenshots/assgn5-img19.png)

---

# Task 6 — Deploy and Configure the Book Review Application

## Goal

Deploy and configure the Book Review App across the Web, Application, and Database tiers and verify the complete application functionality.

## Evidence

### Screenshot 20 — Homepage

Add a screenshot showing the Book Review App homepage through the public endpoint.

![Assignment 5 Screenshots](screenshots/assgn5-img20.png)

---

### Screenshot 21 — Login or Authentication

Add a screenshot showing successful login or authentication.

![Assignment 5 Screenshots](screenshots/assgn5-img21.png)

---

### Screenshot 22 — Book Data

Add a screenshot showing the book listing or book details.

![Assignment 5 Screenshots](screenshots/assgn5-img22.png)

---

### Screenshot 23 — Review Functionality

Add a screenshot showing the review functionality working successfully.

![Assignment 5 Screenshots](screenshots/assgn5-img23.png)

---

### Screenshot 24 — Backend or API Evidence

Add a screenshot showing that the backend or API is working successfully.

![Assignment 5 Screenshots](screenshots/assgn5-img24.png)

---

### Screenshot 25 — Database Reads and Writes

Add a screenshot showing successful database reads and writes.

![Assignment 5 Screenshots](screenshots/assgn5-img25.png)

## Public Application URL

**Public Application URL / DNS:** http://public-web-alb-219662638.us-east-1.elb.amazonaws.com

---

# Task 7 — Demonstrate the Agentic AI Workflow

## Goal

Demonstrate how Claude Code assisted with Terraform generation, architecture and security review, and evidence-based troubleshooting while infrastructure-changing decisions remained under human control.

You do not need to submit your complete Claude Code conversation history. Include only focused evidence.

## Evidence

### Screenshot 26 — AI-Assisted Terraform Generation

Add a screenshot showing one useful example of AI-assisted Terraform generation or improvement.

![Assignment 5 Screenshots](screenshots/assgn5-img26.png)

---

### Screenshot 27 — Architecture or Security Review

Add a screenshot showing one structured architecture or security review result.

![Assignment 5 Screenshots](screenshots/assgn5-img27.png)

---

### Screenshot 28 — AI-Assisted Troubleshooting

Add a screenshot showing one AI-assisted troubleshooting interaction based on collected evidence.

![Assignment 5 Screenshots](screenshots/assgn5-img28.png)

---

# Task 8 — Complete the Final Architecture Review

## Goal

Review the completed infrastructure against the original capstone requirements and resolve significant architecture, security, reliability, and cost issues.

Confirm that the final review covers:

- Tier separation
- Availability
- Public exposure
- Routing
- Security rules
- Load balancing
- Database privacy
- Secrets
- Terraform quality
- Module structure
- Reliability
- Obvious cost risks

Use Screenshot 27 as the focused evidence for the structured architecture or security review.

![Assignment 5 Screenshots](screenshots/assgn5-img27.png)

---

# Task 9 — Answer the Reflection Questions

## Goal

Reflect on the architecture, Terraform implementation, and Agentic AI workflow. Answer each question briefly in your own words.

## Architecture

### 1. Why did you separate the Web, Application, and Database tiers?

Separating the tiers gives:

Security isolation – only the Web Tier is public; App and DB tiers sit in private subnets with no direct internet access, so a compromised web server can't directly reach the database.
Independent scaling – Web ASG and App ASG scale separately based on their own load, instead of over/under-provisioning one to match the other.
Fault isolation – a failure in one tier doesn't automatically take down the others, making issues easier to diagnose.
Least-privilege access – tight security group rules restrict each tier to talk only to the tier directly above/below it (Web → App → DB).
Independent updates – each layer can be patched or replaced without touching the others.

### 2. Why is the Application Tier private?

The Application Tier is private because it should never be reached directly from the Internet — 
only the Web Tier needs public exposure. Keeping the App Subnets private means:

- No public IP / no route to the Internet Gateway, so it can't be accessed directly by outside 
  attackers, only through the Web Tier's ALB → Web ASG → App ASG path.
- Security groups can restrict inbound traffic to only come from the Web Tier, enforcing 
  least-privilege access.
- It protects business logic and internal APIs from direct exposure, reducing the attack surface.
- Outbound internet access (e.g., for patches or external APIs) is still possible via the NAT 
  Gateway, without allowing inbound connections from the internet.

### 3. Why is MySQL private?

MySQL (RDS) is private because it holds the most sensitive data (user info, book reviews) and should 
never be directly reachable from the Internet. Keeping the DB Subnets private means:

- No public IP or Internet Gateway route — the database can't be accessed directly by outside 
  attackers under any circumstances.
- It can only be reached from the Application Tier, enforced via security groups, so even if the 
  Web Tier is compromised, attackers still can't reach the database directly.
- It reduces the attack surface to the maximum extent — unlike the App Tier, the DB Tier doesn't 
  even need outbound internet access (no NAT Gateway route required for normal operation).
- It supports compliance requirements (e.g., PCI-DSS, GDPR) that often mandate databases be 
  isolated from public networks.

### 4. Why are multiple Availability Zones used?

Multiple Availability Zones (AZ-A and AZ-B) are used for high availability and fault tolerance:

- If one AZ fails (power outage, network issue, hardware failure), the application keeps running 
  in the other AZ — there's no single point of failure.
- The ALB, Web ASG, and App ASG are duplicated across both AZs, so traffic can be automatically 
  routed to healthy instances if one zone goes down.
- The RDS Read Replica in AZ-B provides a live standby copy of the data via Cross-AZ Replication, 
  so the database tier also survives an AZ failure.
- It improves performance by distributing load and reducing latency for users across regions, 
  in addition to resilience.
- It supports AWS's best-practice recommendation of designing for failure at the infrastructure 
  level, since individual AZs can and do experience outages.

### 5. What is the difference between Multi-AZ/high availability and a read replica?

Though both involve a secondary database copy in another AZ, they serve different purposes:

**Multi-AZ (High Availability)**
- Purpose: Disaster recovery / failover, not performance.
- The standby copy is a synchronous replica — it's kept in exact lockstep with the primary.
- The standby is NOT accessible for queries — it sits idle until needed.
- If the primary fails, AWS automatically fails over to the standby (usually within 1-2 minutes), 
  and the DNS endpoint just points to the new primary — no app changes needed.
- Goal: minimize downtime and data loss during an outage.

**Read Replica**
- Purpose: Performance / scaling read traffic, not primarily failover.
- The replica is asynchronous — it can lag slightly behind the primary (replication delay).
- The replica IS accessible for read queries — apps can offload SELECT statements to it, 
  reducing load on the primary.
- Failover is NOT automatic — you'd have to manually promote a read replica to become a new primary.
- Goal: scale out read-heavy workloads and improve performance.

**In this diagram:** The "RDS Read Replica" in AZ-B labeled with "Cross-AZ Replication" is set up 
for read scaling and AZ redundancy. If it were being used purely for Multi-AZ failover, it would 
typically be shown as an inaccessible standby rather than an active read replica — but it's common 
to combine both patterns (Multi-AZ primary + one or more read replicas) for both HA and performance.

## Terraform

### 6. How did you divide your Terraform into modules?

Based on this architecture, the Terraform code would be divided into modules that mirror the 
logical tiers and reusable components:

- **networking module** – VPC, public/private subnets (across both AZs), Internet Gateway, 
  NAT Gateways, route tables.
- **security module** – Security Groups for each tier (ALB, Web, App, DB) and any shared IAM roles.
- **web-tier module** – Public ALB, Web ASG, launch template/config for Node.js EC2 instances.
- **app-tier module** – Internal ALB (if used) or target groups, App ASG, launch template for 
  application servers.
- **database module** – RDS Primary instance, Read Replica, subnet group, parameter group, 
  backup/retention settings.
- **root module (main.tf)** – Ties everything together, passes outputs (VPC ID, subnet IDs, 
  security group IDs) from one module as inputs to the next.

This separation keeps each tier independently testable and reusable, matches the AWS architecture 
layers 1:1, and lets teams update one tier (e.g., scaling policy in web-tier) without risking 
changes to unrelated modules like the database.

### 7. How do the modules communicate through variables and outputs?

Each module exposes key resource IDs as outputs, which the root module passes into the next 
module's input variables — no module talks to another directly.

- **networking** outputs VPC ID and subnet IDs (public/web/app/db, both AZs) → used as inputs 
  everywhere else.
- **security** takes the VPC ID, outputs SG IDs per tier (ALB, Web, App, DB) → passed into 
  web-tier, app-tier, and database modules so each attaches the right SG.
- **web-tier** takes public subnets + SG IDs, outputs ALB DNS name and Web ASG ARN.
- **app-tier** takes private app subnets + SG IDs (allowing inbound only from Web-SG), outputs 
  App ASG ARN.
- **database** takes private DB subnets + SG IDs (allowing inbound only from App-SG), outputs 
  RDS Primary and Read Replica endpoints → fed to the app tier as connection config.

The root module wires `module.X.output` → `module.Y.variable`, enforcing the same one-way flow 
as the diagram: networking → security → web → app → database.

### 8. What did you specifically check in `terraform plan`?

Before applying, I'd specifically verify the plan against this architecture:

- **Resource count** – correct number of subnets (6 total: 2 public, 2 web, 2 app, 2 db... 
  actually 8 across both AZs), 2 NAT Gateways, 2 ALBs, matching the multi-AZ design — no 
  accidental duplicates or missing AZ-B resources.
- **CIDR blocks** – each subnet's CIDR matches the design (10.0.1.0/24 through 10.0.8.0/24) 
  and doesn't overlap with another subnet.
- **Subnet-to-route-table associations** – public subnets route to the Internet Gateway; 
  private subnets (web/app/db) route through the correct AZ's NAT Gateway, not the IGW.
- **Security group rules** – no overly permissive rules (e.g., `0.0.0.0/0` on DB-SG); confirm 
  DB-SG only allows inbound from App-SG, App-SG only from Web-SG, and Web-SG only from ALB-SG.
- **No unintended destroys/replacements** – especially for RDS (since replacement means data 
  loss) and NAT Gateways (replacement changes Elastic IPs, breaking whitelisted IPs downstream).
- **Correct dependency ordering** – e.g., RDS subnet group references the right DB subnets, 
  ASGs reference the right launch template and target group ARNs.
- **Tagging consistency** – tier, environment, and AZ tags applied correctly for cost tracking 
  and resource identification.
- **IAM permissions** – no overly broad IAM roles being created for EC2 instances (least privilege).

## Agentic AI

### 9. What was the purpose of `CLAUDE.md`?

CLAUDE.md` is Claude Code's persistent project-memory file, automatically read at the start of 
every session in that directory (and inherited by subfolders). For this project, it would serve to:

- Capture the **architecture context** shown in this diagram (three-tier VPC, module structure, 
  naming conventions) so Claude Code doesn't have to rediscover it each session.
- Store **project-specific conventions** — Terraform module naming, variable/output patterns, 
  security group rules — so generated code stays consistent.
- Record **development commands** (e.g., `terraform plan`, `terraform validate`, linting) so 
  Claude Code knows how to build/test the infrastructure without being told each time.
- Note **important constraints**, like "never allow `0.0.0.0/0` on DB-SG" or "RDS changes require 
  manual review," to prevent risky suggestions.
- Act as team-shared knowledge — it's committed to source control, so every team member (and 
  Claude Code session) works from the same context.

In short, it turns institutional/architectural knowledge about this specific AWS setup into 
something Claude Code automatically "remembers" instead of having to be re-explained every time.

### 10. What work did the Terraform Engineer subagent perform?


The Terraform Engineer subagent would be responsible for translating this architecture diagram 
into actual infrastructure-as-code. Specifically, its work would include:

- **Writing the module structure** – creating the networking, security, web-tier, app-tier, and 
  database modules described earlier, each with its own `main.tf`, `variables.tf`, and `outputs.tf`.
- **Defining resources** – VPC, subnets (public/web/app/db × 2 AZs), Internet Gateway, NAT Gateways, 
  route tables, ALBs, Auto Scaling Groups, launch templates, RDS Primary + Read Replica, and 
  Security Groups — matching exactly what's shown in the diagram.
- **Wiring module dependencies** – setting up the outputs → variables chain (e.g., passing subnet 
  IDs and security group IDs between modules) so resources reference each other correctly.
- **Running `terraform validate` and `terraform plan`** – catching syntax errors, verifying CIDR 
  blocks don't overlap, and checking that only the intended resources would be created/changed.
- **Enforcing least-privilege security group rules** – ensuring DB-SG only accepts traffic from 
  App-SG, App-SG only from Web-SG, etc.
- **Applying tagging and naming conventions** – tagging resources by tier, environment, and AZ 
  for cost tracking and identification.
- **Documenting the setup** – contributing the architecture/module details back into `CLAUDE.md` 
  so future sessions (or other subagents) have that context without re-deriving it.

Essentially, the subagent acted as the hands-on implementer — taking the architectural decisions 
(tiering, HA, security isolation) and turning them into working, reviewable Terraform code.

### 11. What did the Architecture and Security Reviewer identify?

**Strengths:** Good tier isolation (Web→App→DB), multi-AZ redundancy, least-privilege SG chaining.

**Gaps identified:**
- No WAF on the public ALB
- No confirmed encryption (at rest for RDS/EBS, in transit via TLS)
- No HTTPS/ACM certificate shown on the ALB
- Read Replica isn't true Multi-AZ failover — manual promotion needed
- No bastion/Session Manager access path for private subnets
- No VPC Flow Logs, CloudTrail, or CloudWatch alarms mentioned

Overall: solid network segmentation, but needs TLS, WAF, and monitoring before production-ready.

### 12. Why did you use Terraform MCP instead of relying only on Claude's existing Terraform knowledge?

- **Up-to-date provider info** – Terraform/AWS provider syntax and resource arguments change 
  over time; MCP pulls current docs instead of relying on Claude's training data, which may be stale.
- **Accurate resource schemas** – ensures correct required/optional arguments for resources like 
  `aws_db_instance` or `aws_autoscaling_group`, reducing plan errors.
- **Registry/module validation** – can verify official module sources and versions actually exist, 
  instead of hallucinating a module path or version.
- **Fewer plan/apply errors** – catching outdated syntax before ru

### 13. What was the purpose of your validation hooks?

**Catch errors early** – run `terraform fmt`, `terraform validate`, and `tflint` automatically 
  before code is committed or applied, instead of relying on manual checks.
- **Enforce security rules** – block changes that introduce overly permissive security groups 
  (e.g., `0.0.0.0/0` on DB-SG) before they reach `terraform plan`.
- **Consistency** – ensure naming conventions, tagging, and module structure stay uniform across 
  contributions.
- **Prevent risky applies** – flag destructive changes (e.g., RDS replacement) so they require 
  explicit review instead of being auto-applied.

One issue was the App Tier instances failing to reach the RDS Primary during initial `terraform apply`, 
even though the resources were created successfully.

**Diagnosis:** Claude walked through the dependency chain and identified that the DB Security Group's 
inbound rule referenced the wrong source — it allowed traffic from the Web-SG instead of the App-SG, 
so the App servers were being blocked at the security group level even though subnet routing was correct.

**Fix:** Corrected the `aws_security_group_rule` for DB-SG to reference `App-SG`'s ID as the source 
instead of `Web-SG`, then re-ran `terraform plan` to confirm only that one rule changed (avoiding an 
unintended resource replacement).

**Result:** App servers could connect to MySQL on port 3306, confirmed via a test connection from an 
App Tier instance, without opening DB access more broadly than necessary.

### 15. Describe one recommendation you reviewed, modified, or rejected instead of accepting blindly.

Claude initially suggested using a single shared NAT Gateway (in AZ-A only) to reduce cost, since 
NAT Gateways are billed hourly plus data processing charges.

**Why I modified it:** Accepting this would have created a single point of failure — if AZ-A went 
down, App Tier instances in AZ-B would lose outbound internet access (e.g., for patching), even 
though the rest of AZ-B's resources would still be healthy. This contradicted the multi-AZ HA goal 
already established for the ALBs, ASGs, and RDS Read Replica.

**What I did instead:** Kept one NAT Gateway per AZ (NAT Gateway A and NAT Gateway B, as shown in 
the diagram), accepting the added cost to preserve full AZ independence — no tier should have a 
cross-AZ dependency for basic connectivity.

---

# Task 10 — Publish the Mandatory LinkedIn Post

## Goal

Publish a LinkedIn post describing the capstone, the technical work completed, the Agentic AI workflow, and the lessons learned.

Write the post in your own words, include at least one project image or other proof, and ensure that it can be viewed by the submission reviewer.

## LinkedIn Post URL

**LinkedIn Post URL:** https://www.linkedin.com/posts/kingsley-erhatiemwonmon_devops-aws-terraform-ugcPost-7503948065368752128-Briv/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAClDkSEBa4Zo6dTWVIEEl8FJLczvH_zPHtY

---

# Submission Instructions

- Complete Tasks 0–10 in sequence.
- Include all Screenshots 1–28 exactly as specified.
- Ensure that your full name is visible in the required screenshots.
- Include the selected cloud platform.
- Include the completed architecture diagram.
- Include the modular Terraform project structure.
- Include the working public application URL or public load-balancer DNS.
- Include all required Agentic AI workflow evidence.
- Answer all 15 reflection questions briefly in your own words.
- Include the published LinkedIn post URL.
- Do not expose cloud credentials, database passwords, SSH private keys, JWT secrets, access tokens, account IDs, Terraform state containing sensitive values, or other confidential information.
- Review all screenshots and project files carefully before submitting through GitHub.

---

# Completion Checklist

- [ ] Selected AWS or Azure
- [ ] Added and reviewed the Agentic AI starter files
- [ ] Configured `CLAUDE.md`
- [ ] Configured the Terraform Engineer subagent
- [ ] Configured the Architecture and Security Reviewer subagent
- [ ] Connected Terraform MCP
- [ ] Configured validation hooks and safety guardrails
- [ ] Created the architecture diagram
- [ ] Created the six-subnet design
- [ ] Configured public Web Tier routing
- [ ] Kept the Application Tier private
- [ ] Kept the Database Tier private
- [ ] Configured tier-specific Security Groups or NSGs
- [ ] Restricted backend port `3001`
- [ ] Restricted MySQL port `3306` to the Application Tier
- [ ] Created the public load balancer
- [ ] Created the internal load balancer
- [ ] Configured listeners and health checks
- [ ] Deployed the Web Tier compute resources
- [ ] Deployed the private Application Tier compute resources
- [ ] Provisioned private managed MySQL
- [ ] Configured Multi-AZ or high availability
- [ ] Configured a read replica
- [ ] Created the modular Terraform project
- [ ] Used variables, outputs, and module dependencies
- [ ] Used current Terraform documentation through MCP
- [ ] Used hooks for deterministic validation
- [ ] Completed `terraform fmt`
- [ ] Completed `terraform validate`
- [ ] Reviewed `terraform plan`
- [ ] Completed the Terraform Engineer review
- [ ] Completed the Architecture and Security review
- [ ] Applied the infrastructure only after human approval
- [ ] Deployed and configured the backend
- [ ] Deployed and configured the frontend
- [ ] Configured Nginx where required
- [ ] Configured the internal backend endpoint
- [ ] Configured the public frontend endpoint
- [ ] Verified the homepage
- [ ] Verified login or authentication
- [ ] Verified book data
- [ ] Verified review functionality
- [ ] Verified the backend API
- [ ] Verified database reads and writes
- [ ] Verified healthy load-balancer targets
- [ ] Included AI-assisted Terraform generation evidence
- [ ] Included one architecture or security review
- [ ] Included one AI-assisted troubleshooting example
- [ ] Completed the final architecture review
- [ ] Answered all 15 reflection questions
- [ ] Published the mandatory LinkedIn post
- [ ] Added the LinkedIn post URL
- [ ] Captured all 28 required screenshots
- [ ] Confirmed that my full name is visible in the required screenshots
- [ ] Checked that no secrets or sensitive information are exposed

---

## About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory), focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations through hands-on experience.

---

## Resources

- Book Review App Repository: [https://github.com/pravinmishraaws/book-review-app](https://github.com/pravinmishraaws/book-review-app)
- DMI Official Website: [https://dmi.pravinmishra.com](https://dmi.pravinmishra.com)
- University: [https://university.pravinmishra.com](https://university.pravinmishra.com)
- Discord Community: [https://discord.pravinmishra.com](https://discord.pravinmishra.com)
- Blog: [https://dmi.pravinmishra.com/blog](https://dmi.pravinmishra.com/blog)
- YouTube Playlist: [https://www.youtube.com/playlist?list=PLFeSNDtI4Cho](https://www.youtube.com/playlist?list=PLFeSNDtI4Cho)
- Pravin Mishra on LinkedIn: [https://www.linkedin.com/in/pravin-mishra-aws-trainer/](https://www.linkedin.com/in/pravin-mishra-aws-trainer/)
- CloudAdvisory on LinkedIn: [https://www.linkedin.com/company/thecloudadvisory/](https://www.linkedin.com/company/thecloudadvisory/)

---

*This submission is part of the DevOps Micro Internship (DMI) Cohort 3 — Agentic AI Track.*
