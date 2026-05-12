# BUDHA — Bot for Kubernetes Usability, Diagnostics, Health & Analytics

> Built during Hewlett Packard Enterprise internship — Catch Them Young Program (2022–2023)  
> Team project — group of 4 interns working under HPE engineering managers  
> Built with Python, Kubernetes, Flask

---

## Background

During the **Catch Them Young** internship program at **Hewlett Packard Enterprise (HPE)**, a team of 4 interns was assigned to build a real-world Kubernetes diagnostics tool under the guidance of HPE engineering managers.

The goal was to address a genuine pain point in Kubernetes operations — routine cluster diagnostics require deep knowledge of kubectl commands and produce verbose, hard-to-parse output. BUDHA solves this by wrapping cluster operations in a conversational interface that any operator can use, regardless of Kubernetes expertise level.

---

## What Is BUDHA?

BUDHA (**B**ot for **K**ubernetes **U**sability, **D**iagnostics, **H**ealth & **A**nalytics) is a conversational assistant for Kubernetes cluster management. Instead of manually running kubectl commands, operators ask BUDHA natural language questions about cluster health, pod status, node performance, and system logs — and get structured, readable responses instantly.

---

## My Contributions

Working as part of the 4-person intern team under HPE engineering managers, my specific contributions included:

- Designed and implemented Kubernetes diagnostics features for querying pod status, node health, and cluster state
- Contributed to system design of the diagnostics pipeline and conversational query mapping
- Built debugging workflows for identifying and resolving common cluster issues (pod failures, node pressure, resource bottlenecks)
- Integrated health check queries into the conversational interface, enabling natural language access to live cluster data
- Collaborated on testing and validation against a real Kubernetes cluster deployed via kubeadm

---

## Features

- **Conversational interface** — query your cluster in plain English, no kubectl knowledge required
- **Cluster health monitoring** — pod status, node availability, CPU/memory pressure
- **Diagnostics assistance** — identify failing pods, unhealthy nodes, and resource bottlenecks
- **Analytics and insights** — cluster-level summaries and usage patterns
- **Debugging workflows** — guided resolution steps for common Kubernetes issues
- **Log querying** — fetch and filter recent pod logs via natural language

---

## How It Works

```
User types natural language query
          ↓
BUDHA parses intent and maps to kubectl operation
          ↓
Fetches live data from Kubernetes cluster via API
          ↓
Returns structured, readable response to user
```

**Example interactions:**

```
User:  "Which pods are failing?"
BUDHA: Lists pods in CrashLoopBackOff or Error state with namespace and age

User:  "What's the health of my nodes?"
BUDHA: Reports node Ready/NotReady status, CPU pressure, memory pressure

User:  "Show me recent errors in the default namespace"
BUDHA: Returns recent pod logs filtered by error level

User:  "How many pods are running?"
BUDHA: Returns pod count by status across all namespaces
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python, Flask |
| Kubernetes Integration | kubectl, Kubernetes Python client |
| Conversational Interface | Python intent parsing |
| Cluster Setup | kubeadm + containerd |
| Environment | VirtualBox + Ubuntu (local Kubernetes cluster) |

---

## Setting Up Locally

**Prerequisites:** VirtualBox, Ubuntu, Python 3, kubectl configured

```bash
# 1. Clone the repo
git clone https://github.com/prerana-puttaswamy/budhabot_for_kuberenetes_cluster.git
cd budhabot_for_kuberenetes_cluster/budhabot

# 2. Install dependencies
pip3 install -r requirements.txt

# 3. Verify kubectl is configured and pointing to your cluster
kubectl cluster-info

# 4. Run the bot
python3 app.py
```

**Setting up a local Kubernetes cluster with kubeadm and containerd:**  
Refer to: [How to Deploy Kubernetes with kubeadm and containerd](https://thenewstack.io/how-to-deploy-kubernetes-with-kubeadm-and-containerd/)

---

## Project Structure

```
budhabot_for_kuberenetes_cluster/
├── budhabot/
│   ├── app.py              # Main application entry point
│   ├── diagnostics.py      # Kubernetes diagnostics queries
│   ├── health.py           # Cluster health monitoring
│   ├── analytics.py        # Usage analytics and insights
│   └── requirements.txt
└── README.md
```

---

## Evolution: From BUDHA to KubeGPT

BUDHA was an early exploration of Kubernetes conversational interfaces built during the HPE internship. The experience of diagnosing real cluster issues during this project directly inspired [KubeGPT Dashboard](https://github.com/prerana-puttaswamy/kubegpt-dashboard) — a more advanced independent project that adds:

| Feature | BUDHA | KubeGPT |
|---|---|---|
| Interface | Conversational text | Web dashboard |
| Analysis | Rule-based queries | Hybrid: rules + LLM fallback |
| AI | None | Ollama (local LLM) |
| Output | Text responses | Structured incident reports |
| Deployment | Local Python | Docker Compose |

The progression from BUDHA → KubeGPT shows a natural evolution from team exploration to production-grade solo implementation.

---

## Program Context

**Catch Them Young** is an HPE initiative that recruits early-career engineers and assigns them to real engineering projects under the mentorship of senior HPE managers. Teams work on production-relevant problems with the same tools and standards used by HPE engineering teams.

---

## Author

**Prerana Puttaswamy** (Contributor)  
Software Engineering Intern, Hewlett Packard Enterprise (2022–2023)  
MS Computer Science, California State University, Long Beach  
[GitHub](https://github.com/prerana-puttaswamy) | [LinkedIn](https://www.linkedin.com/in/prerana-puttaswamy-a07836224/) | [Portfolio](https://preranap.vercel.app)

> Original repository: [priyaanca/budhabot_for_kuberenetes_cluster](https://github.com/priyaanca/budhabot_for_kuberenetes_cluster)
