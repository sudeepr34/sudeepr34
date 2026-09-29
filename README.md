# Sudeep Reddy

**Site Reliability Engineer — payments infrastructure @ PhonePe, Bengaluru**

I keep high-traffic fintech systems up. Primary on-call for payment platforms serving
**700M+ users**; previously ran 24×7 operations for Visa's **450 PB** Hadoop estate.
My day is incident response, multi-region HA/DR, observability, and automating away toil.

- **Now:** SRE — Ops @ PhonePe. Active-active MySQL Galera across Azure + two on-prem DCs, production Kubernetes, SLOs and error budgets, chaos/failure-injection testing.
- **Before:** Platform Engineer (SRE) @ Altimetrik for Visa. HDFS/Hive/Presto, Airflow at 500+ daily pipelines, Terraform + Ansible provisioning, Kerberos/LDAP/IAM.
- **Interested in:** AIOps — transformer models for anomaly detection, LLMs for alert correlation and RCA drafting.
- **Certified:** Oracle Cloud Infrastructure 2025 DevOps Professional. MBA in Data Science (Amity, 8.4/10).

🌐 [sudeepreddy.vercel.app](https://sudeepreddy.vercel.app) · ✉️ sudeepreddy340@gmail.com

---

## Stack

| Area | Tools |
| --- | --- |
| **Cloud** | AWS (EC2, S3, Route 53, IAM, CloudWatch, EMR, VPC), Azure (Cosmos DB, VNets), OCI |
| **Orchestration** | Kubernetes, Docker, Podman, Helm, Drove |
| **IaC & config** | Terraform, Ansible, SaltStack |
| **CI/CD** | GitLab CI/CD, Jenkins, Harbor, release orchestration |
| **Observability** | Prometheus, Grafana, ELK, Splunk, OpenSearch, PagerDuty |
| **Data** | MySQL, Percona, Galera, Aerospike, Hadoop, Hive, Presto, Spark/YARN |
| **Automation** | Python, Bash, Airflow, Control-M |
| **Networking** | TCP/IP, DNS, BGP, VLAN/VXLAN, NGINX, NAT, firewalls |

## Things I've built

Production work at PhonePe and Visa lives behind the firewall, so these are the
public, reproducible version of how I approach reliability problems.

**[Transformer-Based Anomaly Detection](https://github.com/sudeepr34/Transformer-Based-Anomaly-Detection-System)** — A transformer
encoder autoencoder (TensorFlow/Keras) that scores windows of multi-metric
telemetry. Trained on healthy traffic only, so an unreconstructable window is an
abnormal one. Threshold is calibrated on a validation split against a precision
floor and applied unchanged to test: **precision 0.95, recall 0.83, ROC AUC
0.97.** Returns a per-metric breakdown of the error, so a detection says *which*
metric broke its correlation rather than just "something is wrong". Documented
weak spot: mild traffic drops (recall 0.73) need day-over-day context a single
window doesn't carry.

**[Incident RCA Pipeline](https://github.com/sudeepr34/LLM-Powered-Incident-RCA-Pipeline)** — Correlates Prometheus and
ELK alerts into service clusters, ranks them by severity rather than volume (one
critical outranks five warnings), and tags clusters as origin, correlated, or a
separate incident against a time window. Drafts runbook steps from the signals
actually present in the alert text. Optional LLM summary via local Ollama or any
OpenAI-compatible endpoint, with prompt redaction for IPs and credentials — and
a deterministic fallback on every failure path, because a summariser that breaks
during an outage is worse than none.

**[ansible-roboshop](https://github.com/sudeepr34/ansible-roboshop)** — An 11-service microservice stack provisioned end
to end with Ansible: EC2 + Route 53, MongoDB, Redis, MySQL, RabbitMQ, and seven
app tiers with systemd units and NGINX.

**[shell-roboshop](https://github.com/sudeepr34/shell-roboshop)** — The same stack in idempotent Bash with logging and
error handling — what automating a deploy looks like before you have a
config-management tool.

**[terraform](https://github.com/sudeepr34/terraform)** — Patterns I reach for: remote state, loops and
conditionals, data sources, multi-environment layouts.

**[Portfolio](https://github.com/sudeepr34/Portfolio)** — Dependency-free static site, no framework and no build
step. Strict CSP with no `unsafe-inline`, security headers, and a local dev
server that replays production headers so header breakage shows up before
deploy.

## Currently

Running Gemma offline in a home lab, paired with a log-streaming layer, to
prototype an incident-response assistant that summarises outages and drafts RCA
steps without data leaving the infrastructure.
