# Sudeep Reddy

**Site Reliability Engineer @ PhonePe · Bengaluru**

Primary on-call for payment platforms serving 700M+ users. Previously ran
24×7 ops for Visa's 450 PB Hadoop estate (Altimetrik). Day-to-day: incident
response, multi-region HA/DR, observability, and cutting toil.

- **PhonePe (Dec 2025 – present)** — active-active MySQL Galera across Azure +
  on-prem, production Kubernetes, SLOs / error budgets, chaos testing
- **Altimetrik / Visa (2023 – 2025)** — HDFS / Hive / Presto, Airflow
  (500+ daily pipelines), Terraform + Ansible, Kerberos / LDAP / IAM
- **Also** — OCI 2025 DevOps Professional · MBA Data Science (Amity, 8.4/10)

[Portfolio](https://sudeepreddy.vercel.app) · sudeepreddy340@gmail.com

---

## Stack

| | |
| --- | --- |
| Cloud | AWS (EC2, S3, Route 53, IAM, CloudWatch, EMR, VPC), Azure, OCI |
| Orchestration | Kubernetes, Docker, Podman, Helm, Drove |
| IaC | Terraform, Ansible, SaltStack |
| CI/CD | GitLab CI/CD, Jenkins, Harbor |
| Observability | Prometheus, Grafana, ELK, Splunk, OpenSearch, PagerDuty |
| Data | MySQL, Percona, Galera, Aerospike, Hadoop, Hive, Presto, Spark |
| Scripting | Python, Bash, Airflow, Control-M |
| Networking | TCP/IP, DNS, BGP, VLAN/VXLAN, NGINX, NAT, firewalls |

## Projects

Prod work stays behind the firewall. These are the public versions.

**[Transformer-Based Anomaly Detection](https://github.com/sudeepr34/Transformer-Based-Anomaly-Detection-System)** —
TensorFlow/Keras transformer autoencoder over multi-metric telemetry. Trained
on healthy traffic; reconstruction error is the score. Test: precision 0.95,
recall 0.83, ROC AUC 0.97. Returns per-metric attribution so a detection says
which metric broke, not just that something did.

**[Incident RCA Pipeline](https://github.com/sudeepr34/LLM-Powered-Incident-RCA-Pipeline)** —
Correlates Prometheus/ELK alerts into severity-ranked clusters, tags them as
origin / correlated / separate, drafts runbook steps from the alert text.
Optional LLM summary (Ollama or any OpenAI-compatible endpoint) with prompt
redaction and a deterministic fallback if the LLM fails.

**[ansible-roboshop](https://github.com/sudeepr34/ansible-roboshop)** —
11-service stack end to end with Ansible (EC2, Route 53, MongoDB, Redis,
MySQL, RabbitMQ, app tiers, systemd, NGINX).

**[shell-roboshop](https://github.com/sudeepr34/shell-roboshop)** —
Same stack in Bash — what a deploy looks like before you pull in Ansible.

**[terraform](https://github.com/sudeepr34/terraform)** —
Remote state, loops, conditionals, data sources, multi-env layouts.

**[Portfolio](https://github.com/sudeepr34/Portfolio)** —
Static site, no framework / build step. Strict CSP, security headers.

## Currently

Running Gemma offline in a home lab with a log stream, as a local
incident-response assistant that drafts RCA steps without data leaving the box.
