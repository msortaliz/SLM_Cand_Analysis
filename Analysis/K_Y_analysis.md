# Candidate Analysis: K_Y

## Candidate Skill Level Assessment
> **Mid-Level SRE, ~3 years SRE experience + 1.5 years prior team lead experience (~4.5 YOE total)**
>
> Key signals: Currently Band 1 SRE with 3+ years tenure at P&G, prior IT Team Lead role involving automation/scripting, Apache Airflow, data pipelines. SRE Foundation certified. Consecutive "Very Strong Impact" performance ratings. Strong automation and scripting background but limited evidence of cloud platform depth (GCP/Azure), IaC, or formal SLM experience.

---

## Initial Assessment Against Job Description (Cloud SRE-SLM)

| Skill Area | Score (1-5) | Rationale |
|------------|:-----------:|-----------|
| SLA/SLO/SLI Management | 2 | No direct evidence of defining or managing SLAs/SLOs/SLIs. SRE Foundation cert provides theoretical knowledge but no demonstrated practical application. |
| Cloud Platforms (GCP/Azure) | 2 | Current SRE role implies some cloud exposure but no specific GCP/Azure services mentioned. Gap in demonstrated cloud-native experience. |
| Scripting/Automation (Python, PowerShell, Go) | 4 | Strong automation background from BCI Central (multiprocessing/multithreading, data extraction scripts, Airflow DAGs). Python proficiency is evident. |
| Infrastructure as Code (Terraform) | 1 | No evidence of Terraform or any IaC tool experience. |
| Containers & Kubernetes | 1 | No mention of Docker or Kubernetes experience. |
| Observability (Prometheus, Grafana, OTEL) | 2 | SRE role likely involves monitoring but no specific tools mentioned. |
| CI/CD & DevOps | 3 | DevOps listed as a skill, Git-based code review experience, some pipeline awareness implied. |
| ITIL / Service Management | 2 | SRE Foundation cert covers some ITIL overlap. No ITIL cert or explicit service management experience documented. |
| Incident Management & RCA | 2 | Current SRE role likely involves incidents but no specific examples provided. |
| Communication & Stakeholder Management | 4 | Prior team lead role with cross-functional coordination (researchers & developers), professional presentation skill listed, manager notes highlight communication growth. |
| Automation / Toil Reduction | 4 | Core strength — automation scripts, optimization tools, Airflow orchestration. Manager notes emphasize continued automation focus. |
| Data Analytics & Reporting | 3 | Data extraction/transformation background from prior role. Skill interest in Data Analytics. Some transferable capability for SLM reporting. |

**Overall Fit Score: 2.5/5** — Strong automation and scripting foundation with leadership soft skills, but significant gaps in cloud platform depth, IaC, containers, and formal SLM/ITIL experience. Would require ramp-up in GCP/Azure services, observability tooling, and service level management practices.

---

## Tier 1 — Foundational Questions

**Q1: What are SLIs, SLOs, and SLAs, and how do they relate to each other?**
- **Strong answer covers:** SLI as the metric (e.g., latency, availability), SLO as the target for that metric, SLA as the contractual agreement with consequences. The hierarchy and how SLOs should be stricter than SLAs to provide buffer.
- **Follow-up if shallow:** "How would you decide which SLIs to measure for a web application?"

**Q2: Explain the concept of an error budget and how it influences engineering decisions.**
- **Strong answer covers:** Error budget = 1 - SLO target. When budget is consumed, shift focus from features to reliability. Balances innovation with stability. Practical examples of error budget policies.
- **Follow-up if shallow:** "What happens when an error budget is exhausted — who decides what action to take?"

**Q3: What is "toil" in the SRE context, and how do you identify it?**
- **Strong answer covers:** Manual, repetitive, automatable, tactical, no enduring value, scales linearly with service growth. Examples of toil vs. overhead. The goal of keeping toil below 50%.
- **Follow-up if shallow:** "Give me an example from your experience where you identified and eliminated toil."

**Q4: Describe the difference between monitoring, observability, and alerting.**
- **Strong answer covers:** Monitoring = collecting predefined metrics; observability = ability to understand internal state from external outputs (metrics, logs, traces); alerting = triggering notifications based on thresholds or conditions. The three pillars of observability.
- **Follow-up if shallow:** "What makes a good alert vs. a noisy one?"

**Q5: What is Infrastructure as Code and why is it important?**
- **Strong answer covers:** Declarative/imperative approaches, version control for infra, reproducibility, drift detection, tools like Terraform/Pulumi. Benefits: consistency, auditability, speed.
- **Follow-up if shallow:** "What problems arise when infrastructure is managed manually?"

**Q6: Explain the basics of containerization — what problem does Docker solve?**
- **Strong answer covers:** Process isolation, consistent environments (dev/staging/prod parity), lightweight vs VMs, image layers, Dockerfile basics. Why containers matter for microservices.
- **Follow-up if shallow:** "How does Kubernetes extend what Docker provides?"

---

## Tier 2 — Intermediate Questions

**Q1: You're tasked with setting up monitoring for a new cloud service. Walk me through your approach.**
- **Strong answer covers:** Identify critical user journeys → define SLIs (availability, latency, error rate) → instrument with metrics/logs/traces → set meaningful alert thresholds → create dashboards for different audiences → iterate based on incidents.
- **Follow-up if shallow:** "How do you avoid alert fatigue while still catching real issues?"

**Q2: Describe a blameless post-mortem process. What makes it effective?**
- **Strong answer covers:** Timeline reconstruction, root cause vs contributing factors, action items with owners and deadlines, focus on systemic fixes not individual blame, sharing learnings broadly, follow-up on action items.
- **Follow-up if shallow:** "How do you ensure action items from post-mortems actually get completed?"

**Q3: How would you approach automating a repetitive operational task that currently requires manual intervention?**
- **Strong answer covers:** Quantify the toil (frequency, time, risk), assess complexity and ROI, choose appropriate automation approach (script, pipeline, self-healing), implement with proper error handling and observability, validate with gradual rollout, document.
- **Follow-up if shallow:** "How do you decide what NOT to automate?"

**Q4: Explain how you would manage incident escalation during a major outage affecting multiple teams.**
- **Strong answer covers:** Incident commander role, clear communication channels, severity classification, stakeholder updates at regular intervals, parallel workstreams (technical fix + communication), war room coordination, handoffs between time zones.
- **Follow-up if shallow:** "How do you communicate to non-technical leadership during an ongoing incident?"

**Q5: What's the difference between horizontal and vertical scaling, and when would you choose one over the other in a cloud environment?**
- **Strong answer covers:** Vertical = bigger instance, simpler but has limits; horizontal = more instances, requires stateless design or shared state management. Cost implications, availability implications, auto-scaling strategies in GCP/Azure.
- **Follow-up if shallow:** "What challenges does horizontal scaling introduce for stateful applications?"

**Q6: How would you approach migrating an on-prem monitoring solution to a cloud-native observability stack?**
- **Strong answer covers:** Assess current state (what's monitored, what gaps exist), evaluate cloud-native options (Cloud Monitoring, Azure Monitor, Prometheus/Grafana), plan phased migration, ensure no visibility gaps during transition, train the team, validate alert parity.
- **Follow-up if shallow:** "What would you prioritize migrating first and why?"

---

## Tier 3 — Experience-Specific Questions

**Q1 [Re: Current SRE role at P&G — Workday Technology focus]:**
"Your manager notes mention building technical mastery in Workday Technology. What SRE practices have you applied to Workday, and what's unique about ensuring reliability for a SaaS platform you don't fully control?"
- **Strong answer covers:** Monitoring integration points (APIs, integrations), defining SLOs for Workday-dependent processes, automating integration testing, managing vendor SLA expectations, building observability around what you can control (integration layer, data flows).
- **Red flags:** Cannot articulate specific reliability work done on Workday; only describes general admin tasks.
- **Follow-up if shallow:** "What metrics do you track to know if Workday integrations are healthy?"

**Q2 [Re: Apache Airflow management — 1000+ sources/tasks at BCI Central]:**
"You managed 1000+ sources and tasks in Apache Airflow. How did you ensure reliability and observability at that scale?"
- **Strong answer covers:** DAG design patterns for reliability (retries, SLAs, alerting on failures), monitoring DAG performance, managing dependencies, handling backfills, resource management (worker scaling), preventing cascade failures.
- **Red flags:** Only describes writing DAGs, not operating/monitoring them at scale.
- **Follow-up if shallow:** "What happened when a critical DAG failed at 2 AM? Walk me through your response process."

**Q3 [Re: Multiprocessing/Multithreading optimization tools at BCI Central]:**
"You implemented tools using multiprocessing and multithreading for data extraction optimization. Explain a specific performance problem you solved and how you chose between multiprocessing vs. multithreading."
- **Strong answer covers:** Understanding of GIL in Python, I/O-bound vs CPU-bound workloads, specific metrics improvement (e.g., reduced processing time from X to Y), error handling in concurrent code, resource management.
- **Red flags:** Cannot explain when to use one over the other; gives textbook answer without real example.
- **Follow-up if shallow:** "What failure modes did you encounter with concurrent processing, and how did you handle them?"

**Q4 [Re: PDF Extraction tool via Tesseract OCR API]:**
"Walk me through the architecture of your PDF extraction tool. What were the reliability and accuracy challenges?"
- **Strong answer covers:** Pipeline design (PDF → image → OCR → structured data), handling poor-quality scans, accuracy validation, error handling for malformed PDFs, performance optimization, integration with downstream systems.
- **Red flags:** Describes only calling the API without understanding the end-to-end pipeline or quality challenges.
- **Follow-up if shallow:** "How did you measure and improve OCR accuracy? What was your error rate?"

**Q5 [Re: Team Lead experience — coordinating researchers and developers]:**
"As a team lead, how did you handle situations where technical priorities conflicted with researcher timelines or expectations?"
- **Strong answer covers:** Specific examples of trade-off decisions, communication strategies, setting expectations, prioritization frameworks, managing up and across, balancing technical debt with delivery.
- **Red flags:** Generic leadership platitudes without concrete examples.
- **Follow-up if shallow:** "Give me a specific example where you had to say 'no' or push back on a request. How did you handle it?"

**Q6 [Re: Consecutive "Very Strong Impact" ratings + automation focus]:**
"Your performance has been rated Very Strong Impact for two consecutive years. What's the most impactful automation or engineering project you delivered in your current SRE role, and how did you measure its impact?"
- **Strong answer covers:** Specific project with clear before/after metrics (time saved, incidents reduced, reliability improved), how they identified the opportunity, technical approach, stakeholder buy-in, measurable business outcome.
- **Red flags:** Cannot quantify impact; describes effort rather than outcome.
- **Follow-up if shallow:** "How did you prioritize this project over other potential improvements?"

**Q7 [Re: SRE Foundation Certification + current role]:**
"How have you applied concepts from your SRE Foundation certification in your day-to-day work? Give me a specific example where SRE theory changed how you approached a problem."
- **Strong answer covers:** Specific principle (error budgets, SLOs, toil reduction, automation) applied to a real scenario, measurable outcome, how it shifted team practices.
- **Red flags:** Cannot connect certification content to actual work; certification appears purely academic.
- **Follow-up if shallow:** "What SRE practice do you think your team should adopt next, and why?"

**Q8 [Re: Gap — No cloud platform specifics mentioned]:**
"Your resume doesn't specify which cloud platforms or services you work with in your current SRE role. What cloud infrastructure do you support, and what's your hands-on experience with GCP or Azure?"
- **Strong answer covers:** Specific services managed, responsibilities (provisioning, monitoring, troubleshooting), scale of infrastructure, any architecture decisions made.
- **Red flags:** Vague answers suggesting limited direct cloud platform interaction.
- **Follow-up if shallow:** "Have you ever provisioned or configured cloud resources yourself, or is that handled by another team?"

---

## Gaps & Clarification Notes

| Gap Area | Suggested Clarifying Question |
|----------|-------------------------------|
| No GCP/Azure services mentioned | "What cloud services do you interact with daily in your current role?" |
| No IaC (Terraform) experience evident | "Have you written or modified Terraform configurations? If not, how is your infrastructure managed?" |
| No Kubernetes/Docker mentioned | "Does your team use containers? What's your exposure to Kubernetes?" |
| No observability tools specified | "What monitoring/alerting tools do you use today?" |
| No formal SLO/SLI work documented | "Have you been involved in defining or reporting on SLOs in your current role?" |
