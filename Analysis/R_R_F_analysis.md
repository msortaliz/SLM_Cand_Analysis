# Technical Interview Analysis: Candidate R_R_F

---

## Candidate Skill Level Assessment

> **Junior-to-Mid Level SRE, ~1.5 YOE**
>
> **Key Signals:** Hired Dec 2024 as Band 1 SRE (entry-level). Has ITIL 4 Foundation certification (Feb 2026). Received "Strong Impact" rating in FY 24/25. Screening responses reveal significantly more depth than the HR profile alone: implemented Prometheus & Grafana observability stack across 1000+ global servers, automated toil with Puppet and PowerShell (100+ hours saved annually), served as Incident Commander during critical incidents, maintained >90% SLA compliance, drove 30% annual cost reduction through metric optimization, and has Problem Management/Change Management/RCA experience. Skill interests include SRE Observability and GE Proficy.

---

## Screening Question Highlights

| Topic | Key Details from Candidate |
|-------|--------------------------|
| **Motivation** | Strong alignment with cloud SRE path; sees this as next career step to specialize in cloud |
| **SLA/Incident Command** | >90% SLA compliance for critical incidents; served as Incident Commander |
| **Observability** | Implemented comprehensive Prometheus & Grafana stack across 1000+ global servers |
| **Automation** | Puppet and PowerShell automation saving 100+ hours of toil annually |
| **Cost Optimization** | 30% annual cost reduction through metric optimization |
| **Process** | Problem Management, Change Management, RCA/CAP processes |
| **Recognition** | "Team Builder Award" for collaborative leadership |
| **Growth Goals** | Wants to deepen cloud-native skills (GCP/Azure), IaC, chaos engineering |

---

## Initial Assessment Against Job Description (Cloud SRE-SLM)

| Skill / Requirement | Score (1-5) | Rationale |
|---|---|---|
| **SLA/SLO/SLI Management** | 4 | Claims >90% SLA compliance and Incident Commander role. Demonstrates active SLM practice. |
| **Cloud Platforms (GCP & Azure)** | 2 | No specific cloud platform certifications or projects. Candidate acknowledges this is a growth area. |
| **Scripting/Automation (Python, PowerShell, Go)** | 4 | Proven PowerShell and Puppet automation; 100+ hours of toil reduced annually. |
| **Infrastructure as Code (Terraform)** | 2 | Uses Puppet (configuration management) but no Terraform/IaC evidence. Candidate wants to develop this. |
| **Containers (Docker, Kubernetes)** | 1 | No mention of container technologies. |
| **Observability (Prometheus, Grafana, OpenTelemetry)** | 4 | Implemented Prometheus & Grafana across 1000+ servers. Strong hands-on experience. |
| **CI/CD & DevOps Practices** | 2 | "DevOps" listed as a skill; no specific CI/CD pipeline tools mentioned. |
| **ITIL (Incident/Problem/Change Mgmt)** | 5 | ITIL 4 Foundation certified + demonstrated Incident Management, Problem Management, Change Management, and RCA/CAP in practice. |
| **Communication & Stakeholder Management** | 4 | Incident Commander role, "Team Builder Award," articulate screening responses demonstrating clear communication. |
| **Analytical & Problem-Solving** | 4 | RCA/CAP processes, metric optimization leading to 30% cost reduction, data-driven approach. |
| **Incident Response & RCA** | 4 | Incident Commander experience, rigorous RCA and CAP processes mentioned explicitly. |
| **Cost Optimization** | 4 | 30% annual cost reduction through metric optimization — strong signal. |

**Overall Fit Score: 3.3 / 5 (Revised from 2.2)** — Screening responses reveal a much stronger candidate than the HR profile alone suggested. Proven SRE practitioner with hands-on observability (Prometheus/Grafana at scale), automation (PowerShell/Puppet), incident command, and SLM experience. Primary gaps remain in cloud platform depth (GCP/Azure), IaC (Terraform), and containers (Docker/K8s). With mentoring on cloud-specific skills, this candidate has strong potential for the role.

---

## Tier 1 — Foundational Questions

**Q1: What are SLIs, SLOs, and SLAs? How do they relate to each other?**
- **Strong answer covers:** SLI = measurable indicator (e.g., latency, availability), SLO = target threshold for the SLI, SLA = contractual agreement with consequences. SLOs inform SLAs; SLIs are what you actually measure.
- **Follow-up if shallow:** "Can you give me an example of an SLI for a web service and how you'd set its SLO?"

**Q2: Explain the difference between monitoring, alerting, and observability.**
- **Strong answer covers:** Monitoring = collecting predefined metrics; alerting = notifying when thresholds are breached; observability = ability to understand system state from external outputs (logs, metrics, traces). Observability is broader and enables debugging unknown-unknowns.
- **Follow-up if shallow:** "How would you troubleshoot a latency spike if your monitoring dashboards show everything green?"

**Q3: What is ITIL Incident Management and how does it differ from Problem Management?**
- **Strong answer covers:** Incident = restore service ASAP; Problem = find root cause to prevent recurrence. Incidents are reactive; problems are proactive. A single problem can cause multiple incidents.
- **Follow-up if shallow:** "Walk me through how you'd escalate a P1 incident in your current role."

**Q4: What is Infrastructure as Code (IaC) and why is it important?**
- **Strong answer covers:** Declarative definition of infrastructure (e.g., Terraform, Pulumi). Benefits: reproducibility, version control, consistency, drift detection, automation. Contrast with manual/click-ops provisioning.
- **Follow-up if shallow:** "What problems arise if infrastructure is managed manually in a multi-cloud environment?"

**Q5: Explain the concept of "toil" in SRE. Give an example.**
- **Strong answer covers:** Toil = manual, repetitive, automatable work that scales linearly with service growth and has no enduring value. Example: manually restarting pods, manually creating tickets. SRE aims to keep toil below 50% of time.
- **Follow-up if shallow:** "How would you measure toil on your team, and how do you decide what to automate first?"

**Q6: What is a container and how does it differ from a virtual machine?**
- **Strong answer covers:** Containers share host OS kernel, are lightweight, fast to start. VMs have full OS, more isolation, heavier. Containers are ideal for microservices; VMs for workloads needing strong isolation.
- **Follow-up if shallow:** "When would you choose a VM over a container in a cloud deployment?"

---

## Tier 2 — Intermediate Questions

**Q1: How would you design a monitoring and alerting strategy for a new cloud service?**
- **Strong answer covers:** Identify key SLIs (availability, latency, error rate, throughput), set SLOs, create dashboards, define alert thresholds with severity levels, avoid alert fatigue, implement runbooks, use multi-signal alerts.
- **Follow-up if shallow:** "How do you handle alert fatigue? What's your approach to tuning alerts?"

**Q2: Describe the incident response lifecycle from detection to resolution.**
- **Strong answer covers:** Detection (monitoring/alerting) → Triage (severity assessment) → Communication (stakeholders, war room) → Mitigation (restore service) → Resolution (permanent fix) → Post-mortem (blameless RCA, action items). Mention roles: incident commander, comms lead.
- **Follow-up if shallow:** "What makes a good post-mortem? What's the difference between a blameless and blame-oriented culture?"

**Q3: You have a service running on GCP that needs 99.9% availability. How would you architect for this?**
- **Strong answer covers:** Multi-zone or multi-region deployment, load balancing, health checks, auto-scaling, redundant data stores, graceful degradation, error budgets. Calculate: 99.9% = ~8.76 hours downtime/year.
- **Follow-up if shallow:** "What's an error budget and how would you use it to balance reliability vs. feature velocity?"

**Q4: Explain how you would use Terraform to manage cloud infrastructure across GCP and Azure.**
- **Strong answer covers:** Provider blocks for each cloud, state management (remote backend), modules for reusability, workspaces or directory structure for environments, plan/apply workflow, CI/CD integration for IaC.
- **Follow-up if shallow:** "What happens if two people apply Terraform changes at the same time? How do you prevent state conflicts?"

**Q5: How do you prioritize and triage incoming L1/L2 support tickets?**
- **Strong answer covers:** Severity/impact matrix, SLA timers, business impact assessment, categorization, escalation paths, knowledge base for known issues, automation of common resolutions.
- **Follow-up if shallow:** "How would you handle a situation where multiple P2 tickets come in simultaneously and you're short-staffed?"

**Q6: What is the difference between Prometheus and Azure Monitor/Cloud Monitoring? When would you use each?**
- **Strong answer covers:** Prometheus = open-source, pull-based, great for Kubernetes, flexible PromQL. Cloud-native monitors (Azure Monitor, GCP Cloud Monitoring) = integrated, managed, easier setup, better for platform-level metrics. Trade-offs: vendor lock-in vs. operational overhead.
- **Follow-up if shallow:** "How would you unify observability across a multi-cloud (GCP + Azure) environment?"

---

## Tier 3 — Experience-Specific Questions

**Q1 [Re: SRE Role at P&G Manufacturing Services]: What does your day-to-day look like as an SRE? What systems do you support?**
- **Strong answer covers:** Specific services/applications monitored, tools used, on-call responsibilities, types of incidents handled, automation built, collaboration with dev teams.
- **Red flags:** Cannot name specific systems, tools, or metrics. Describes role in purely theoretical terms.
- **Follow-up if shallow:** "Can you walk me through a specific incident you handled from alert to resolution?"

**Q2 [Re: "Strong Impact" Performance Rating]: What accomplishment earned you the "Strong Impact" rating in your first year?**
- **Strong answer covers:** Specific project or initiative, measurable outcome (reduced incidents by X%, automated Y process, improved MTTD/MTTR), ownership demonstrated.
- **Red flags:** Vague ("I worked hard", "I was a team player") without specific deliverables.
- **Follow-up if shallow:** "What was your individual contribution vs. team effort? What would have happened if you hadn't been involved?"

**Q3 [Re: ITIL 4 Foundation Certification]: How have you applied ITIL principles in your current SRE role?**
- **Strong answer covers:** Specific examples of incident management process improvements, change management workflows, problem management (known error databases, RCA), or service level management activities they initiated or improved.
- **Red flags:** Only describes passing the exam; cannot connect ITIL to daily work.
- **Follow-up if shallow:** "Give me an example where an ITIL practice conflicted with SRE principles. How did you reconcile them?"

**Q4 [Re: DevOps Skill]: What DevOps tools and practices do you use in your current role?**
- **Strong answer covers:** Specific CI/CD pipelines, version control workflows, automated testing, deployment strategies (blue/green, canary), collaboration practices between dev and ops.
- **Red flags:** Lists "DevOps" as a buzzword but cannot name specific tools or workflows.
- **Follow-up if shallow:** "Have you built or maintained any CI/CD pipeline? What tools did you use?"

**Q5 [Re: Computer Networking Skill]: How does your networking knowledge apply to your SRE work?**
- **Strong answer covers:** Understanding of DNS, load balancing, firewalls/security groups, VPCs, network latency troubleshooting, CDNs, TCP/UDP, subnet design in cloud environments.
- **Red flags:** Only mentions basic concepts without cloud networking application.
- **Follow-up if shallow:** "Have you ever debugged a network-related incident in a cloud environment? What was the issue?"

**Q6 [Re: Embedded Systems Skill]: How did you gain embedded systems experience and how does it relate to your SRE work?**
- **Strong answer covers:** Background context (academic or prior work), understanding of hardware-software interface, how this translates to understanding manufacturing systems (GE Proficy interest), edge computing, IoT monitoring.
- **Red flags:** Listed without context or applicability.
- **Follow-up if shallow:** "Is this from academic work or professional experience? How has it shaped your approach to reliability?"

**Q7 [Re: SRE Observability Interest & GE Proficy Interest]: What observability tools are you currently using or learning?**
- **Strong answer covers:** Specific tools (Prometheus, Grafana, OpenTelemetry, cloud-native monitoring), what metrics/logs/traces they collect, dashboards built, alerting rules configured. GE Proficy context for manufacturing observability.
- **Red flags:** Only expresses interest without hands-on experience.
- **Follow-up if shallow:** "Have you built any dashboards or alerting rules? What SLIs were you tracking?"

**Q8 [Re: System Administration Skill]: What systems have you administered and what was your approach to maintaining them?**
- **Strong answer covers:** Specific OS environments (Linux/Windows), patch management, configuration management, access control, backup/restore, capacity planning, automation of admin tasks.
- **Red flags:** Generic answers without specifics on scale or complexity.
- **Follow-up if shallow:** "How many systems were you responsible for? What was your patching/update strategy?"

---

## Flagged Gaps & Clarifying Questions

| Gap | Suggested Clarifying Question |
|---|---|
| No cloud platform specifics (GCP/Azure) | "Which cloud platforms do you work with daily? What services do you interact with?" |
| No scripting/automation language specified | "What programming or scripting languages do you use in your role?" |
| No IaC or Terraform mention | "Does your team use Infrastructure as Code? If so, what tools?" |
| No container/Kubernetes experience evident | "Have you worked with Docker or Kubernetes in any capacity?" |
| No work experience or job history prior to P&G | "What were you doing before joining P&G? Any internships or projects?" |
| "Software Engineering" skill without context | "What software have you built or contributed to? What languages/frameworks?" |

---

## Summary Recommendation

This is an early-career SRE (~1.5 years) with strong performance and significantly more hands-on depth than the HR profile alone suggests. Screening responses reveal proven experience with observability at scale (Prometheus/Grafana on 1000+ servers), automation (Puppet/PowerShell, 100+ hours saved), incident command, SLA management (>90% compliance), cost optimization (30% reduction), and formal ITIL processes. The candidate is articulate, motivated, and has a clear growth trajectory toward cloud specialization. Primary gaps are in cloud-native platforms (GCP/Azure services), IaC (Terraform), and containers (Docker/K8s). The interview should validate the screening claims with specifics (Tier 3 questions) and assess cloud platform readiness. With targeted mentoring on cloud-specific skills, this candidate is a **viable hire** for the Cloud SRE-SLM role.
