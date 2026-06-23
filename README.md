# Awesome Base Command Manager

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](./CONTRIBUTING.md)

A curated registry of resources for **NVIDIA Base Command Manager (BCM)** — the standard for provisioning, managing, and monitoring HPC and AI clusters at scale.

The goal is to be the definitive place to discover and install resources that help administrators and users deploy, operate, and optimize BCM clusters: from cmsh provisioning and workload managers to GPU configuration, Kubernetes, Jupyter, Spark, monitoring, and support.

**Inclusion criteria:** Resources must be directly related to Base Command Manager or its closely coupled ecosystem (Slurm, PBS, Kubernetes, Jupyter, Spark, environment modules, MPI, GPU tooling on BCM). See [CONTRIBUTING.md](./CONTRIBUTING.md) for the full quality bar.

---

## Contents

- [Official Documentation and Training](#official-documentation-and-training)
- [Installation and Provisioning](#installation-and-provisioning)
- [Workload Managers](#workload-managers)
- [GPU Configuration](#gpu-configuration)
- [Monitoring and Observability](#monitoring-and-observability)
- [MPI and Parallel Computing](#mpi-and-parallel-computing)
- [Containers and Kubernetes](#containers-and-kubernetes)
- [Jupyter and Interactive Apps](#jupyter-and-interactive-apps)
- [Troubleshooting and Support](#troubleshooting-and-support)
- [Community Tools](#community-tools)
- [Related Awesome Lists](#related-awesome-lists)
- [Notes](#notes)
- [Contributing](#contributing)
- [License](#license)

---

## Official Documentation and Training

Core product documentation, manuals, release notes, and training for NVIDIA Base Command Manager.

- **[NVIDIA Base Command Manager](https://www.nvidia.com/en-us/data-center/base-command-manager/)** `Official` — Product home for BCM, the HPC and AI cluster management platform.
- **[NVIDIA Base Command Manager Documentation](https://docs.nvidia.com/base-command-manager/index.html)** `Official` — Docs hub with manuals for BCM 10 and 11, release notes, and deployment guides.
- **[Base Command Manager 11 Administrator Manual](https://docs.nvidia.com/base-command-manager/manuals/11/admin-manual.pdf)** `Official` — Comprehensive administrator reference for installing, configuring, and managing BCM clusters.
- **[Base Command Manager 11 Installation Manual](https://docs.nvidia.com/base-command-manager/manuals/11/installation-manual.pdf)** `Official` — Step-by-step installation and quickstart guide for bare-metal BCM clusters.
- **[Base Command Manager 11 User Manual](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — End-user guide covering modules, MPI, Slurm, PBS, and job submission.
- **[Base Command Manager 11 Developer Manual](https://docs.nvidia.com/base-command-manager/manuals/11/developer-manual.pdf)** `Official` — Python API, monitoring data producers, and CMDaemon REST API reference.
- **[Base Command Manager 10 Release Notes](https://docs.nvidia.com/base-command-manager/bcm-10-release-notes/)** `Official` — Release notes for the BCM 10 major release line.
- **[Base Command Manager Training](https://www.nvidia.com/en-us/data-center/base-command-manager/)** `Official` — NVIDIA training and certification resources for cluster administrators.

---

## Installation and Provisioning

Resources for installing BCM, provisioning nodes, managing software images, and configuring cluster hardware.

- **[Base Command Manager Installation Manual](https://docs.nvidia.com/base-command-manager/manuals/11/installation-manual.pdf)** `Official` — BCM head-node installation, network setup, and node provisioning.
  - Run: `cm-setup` or `cm-wlm-setup` after head-node install.
- **[Provision a Node with NVIDIA BaseOS in BCM](https://docs.nvidia.com/dgx/baseos-on-bcm-install-guide/index.html)** `Official` — Guide to creating and deploying NVIDIA BaseOS images in BCM.
- **[DGX BasePOD Deployment Guide](https://docs.nvidia.com/dgx-basepod/deployment-guide-dgx-basepod/latest/index.html)** `Official` — BCM-based deployment for DGX BasePOD clusters.
- **[DGX SuperPOD Administration Guide](https://docs.nvidia.com/dgx-superpod/administration-guide-dgx-superpod/latest/index.html)** `Official` — BCM administration procedures for DGX SuperPOD systems.
- **[cmsh Provisioning](https://docs.nvidia.com/base-command-manager/manuals/11/admin-manual.pdf)** `Official` — Use `cmsh` to identify, clone, and provision nodes via PXE or node-installer.
  - Example: `cmsh -c "device newnodes"` to discover pending nodes.
- **[Software Image Management](https://docs.nvidia.com/base-command-manager/manuals/11/admin-manual.pdf)** `Official` — Create, snapshot, update, and assign software images to node categories.
  - Example: `cmsh -c "image; use default-image; snapshot"` to snapshot before changes.

---

## Workload Managers

Resources for configuring and using Slurm, PBS Professional, OpenPBS, and LSF with BCM.

- **[Slurm Workload Manager in BCM](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — User guide for loading Slurm modules, compiling, and submitting jobs.
- **[cm-wlm-setup](https://docs.nvidia.com/base-command-manager/manuals/11/installation-manual.pdf)** `Official` — TUI wizard for installing and configuring Slurm, PBS, or LSF on BCM.
  - Run: `cm-wlm-setup` on the head node.
- **[PBS Professional and OpenPBS in BCM](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — PBS job scripts, directives, and submission workflows on BCM.
- **[Slurm Workload Management in NVIDIA Mission Control](https://docs.nvidia.com/mission-control/docs/systems-administration-guide/2.3.0/slurm-workload-management.html)** `Official` — Mission Control Slurm integration, IMEX, and topology configuration on BCM.
- **[NVIDIA Mission Control Workload Manager Installation](https://docs.nvidia.com/mission-control/docs/nmc-software-installation-guide/2.3.0/nmc-workload-manager-installation.html)** `Official` — Install and validate Slurm on GB200/GB300 NVL72 clusters with BCM.
- **[Slurm on DGX BasePOD](https://docs.nvidia.com/dgx-basepod/deployment-guide-basepod-rhel/latest/slurm.html)** `Official` — Slurm deployment guide for DGX BasePOD with BCM.

---

## GPU Configuration

Resources for configuring NVIDIA GPUs, MIG, CUDA MPS, DCGM, and GPU workload scheduling in BCM.

- **[Configuring GPU Settings in BCM](https://docs.nvidia.com/base-command-manager/manuals/11/admin-manual.pdf)** `Official` — GPU units, GPU settings, and `gpusettings` submode in cmsh.
- **[MIG Configuration in BCM](https://docs.nvidia.com/base-command-manager/manuals/11/admin-manual.pdf)** `Official` — Multi-Instance GPU profiles and autodetection for Slurm `gres.conf`.
  - Run: `cm-mig-manage` or set MIG profiles in cmsh.
- **[CUDA Multi-Process Service with cm-wlm-setup](https://docs.nvidia.com/base-command-manager/manuals/11/installation-manual.pdf)** `Official` — Configure NVIDIA MPS for GPU sharing through the workload-manager setup wizard.
- **[NVIDIA Data Center GPU Manager](https://docs.nvidia.com/datacenter/dcgm/latest/)** `Official` — DCGM for GPU health monitoring in BCM software images.
- **[NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/)** `Official` — Container runtime for GPU workloads used by BCM Docker and Kubernetes setups.

---

## Monitoring and Observability

Resources for BCM monitoring, metrics, health checks, triggers, Prometheus/Grafana, and diagnostics.

- **[BCM Monitoring Infrastructure](https://docs.nvidia.com/base-command-manager/manuals/11/admin-manual.pdf)** `Official` — Metrics, health checks, triggers, actions, and `monitoring` mode in cmsh.
- **[BCM Prometheus Exporter](https://docs.nvidia.com/mission-control/docs/systems-administration-guide/2.3.0/observability.html)** `Official` — Export BCM metrics to Prometheus for Grafana dashboards.
  - Query: `curl -sk https://localhost:8081/exporter`
- **[Observability Stack Configuration in Mission Control](https://docs.nvidia.com/mission-control/docs/nmc-software-installation-guide/2.3.0/nmc-observability-stack-configuration.html)** `Official` — Wire BCM Prometheus endpoints into a Kubernetes observability stack.
- **[Monitoring Data Producers](https://docs.nvidia.com/base-command-manager/manuals/11/developer-manual.pdf)** `Official` — Developer guide for custom metrics, health checks, and Prometheus producers.
- **[cm-diagnose](https://docs.nvidia.com/base-command-manager/manuals/11/admin-manual.pdf)** `Official` — Built-in diagnostic tool to collect cluster state and logs for support.
  - Run: `cm-diagnose` or `cm-diagnose --support` on the head node.

---

## MPI and Parallel Computing

Resources for MPI, environment modules, OpenMP, and parallel job execution on BCM clusters.

- **[Environment Modules in BCM](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — Using `module load`, `module avail`, and `module list` on BCM.
- **[MPI Libraries in BCM](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — MPICH, MVAPICH, Open MPI, and Intel MPI integration via modules.
- **[Open MPI with CUDA Awareness](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — GPU-aware Open MPI for CUDA-accelerated parallel applications.
- **[OpenMP and MPI Examples](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — Sample job scripts for hybrid OpenMP/MPI workloads on BCM.
- **[Machine Learning Manual](https://docs.nvidia.com/base-command-manager/manuals/10/machine-learning-manual.pdf)** `Official` — ML package modules, TensorFlow, and MPI dependencies on BCM.

---

## Containers and Kubernetes

Resources for Docker, Kubernetes, Cluster API, GPU Operator, and Spark on BCM.

- **[BCM Containerization Manual](https://docs.nvidia.com/base-command-manager/manuals/11/containerization-manual.pdf)** `Official` — Docker, Kubernetes, and container management on BCM.
- **[cm-kubernetes-setup](https://docs.nvidia.com/base-command-manager/manuals/11/containerization-manual.pdf)** `Official` — TUI wizard to deploy Kubernetes on BCM nodes.
  - Run: `cm-kubernetes-setup` on the head node.
- **[Cluster API in BCM](https://docs.nvidia.com/base-command-manager/bcm-10-release-notes/)** `Official` — Declarative Kubernetes cluster provisioning with `cm-kubernetes-capi-setup`.
- **[NVIDIA GPU Operator on BCM Kubernetes](https://docs.nvidia.com/dgx-basepod/deployment-guide-dgx-basepod/latest/kube-deploy.html)** `Official` — Deploy the GPU Operator during `cm-kubernetes-setup`.
- **[Run:ai on Base Command Manager](https://run-ai-docs.nvidia.com/self-hosted/2.22/getting-started/installation/bcm-install/deployment)** `Official` — Install NVIDIA Run:ai on a BCM-managed Kubernetes cluster.
- **[Spark on Kubernetes in BCM](https://docs.nvidia.com/base-command-manager/manuals/11/containerization-manual.pdf)** `Official` — Kubernetes Spark Operator and Spark-based Jupyter kernels on BCM.

---

## Jupyter and Interactive Apps

Resources for JupyterHub, JupyterLab, Jupyter kernels, VNC, and interactive workload integration.

- **[cm-jupyter-setup](https://docs.nvidia.com/dgx-basepod/deployment-guides/dgx-basepod-a100/latest/deployment-jupyter.html)** `Official` — CLI wizard to deploy JupyterHub on BCM.
  - Run: `cm-jupyter-setup` on the head node.
- **[Using Jupyter in BCM](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — User guide for Jupyter notebooks, kernels, and extensions on BCM.
- **[Jupyter Kernels for Slurm and PBS](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — Configure Jupyter Enterprise Gateway kernels backed by H workload managers.
- **[Jupyter VNC Extension](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — Launch remote desktop sessions from Jupyter on BCM.
- **[Jupyter WLM Magic Extension](https://docs.nvidia.com/base-command-manager/manuals/11/user-manual.pdf)** `Official` — Magic commands to submit and manage jobs from Jupyter notebooks.

---

## Troubleshooting and Support

Resources for diagnosing BCM issues, node boot problems, logs, and getting support.

- **[Troubleshooting the Node Boot Process](https://docs.nvidia.com/base-command-manager/manuals/11/admin-manual.pdf)** `Official` — Node-installer logs, provisioning logging, and boot diagnostics.
- **[cm-diagnose](https://docs.nvidia.com/base-command-manager/manuals/11/admin-manual.pdf)** `Official` — Collect cluster diagnostics and support bundles.
- **[NVIDIA Enterprise Support](https://www.nvidia.com/en-us/support/enterprise/)** `Official` — Open support cases for Base Command Manager subscriptions.
- **[NVIDIA Developer Forums - Base Command Manager](https://forums.developer.nvidia.com/c/accelerated-computing/base-command-manager/266)** `Community` — Community Q&A, troubleshooting, and best practices.
- **[BCM Cluster on Demand OCI PyPI Package](https://pypi.org/project/cm-cluster-on-demand-oci/)** `Official` — Python CLI to spin up BCM clusters in Oracle Cloud Infrastructure.
  - Install: `pip install cm-cluster-on-demand-oci`

---

## Community Tools

Community and automation resources that extend or interact with BCM.

- **[BCM Developer Manual Python API Examples](https://docs.nvidia.com/base-command-manager/manuals/11/developer-manual.pdf)** `Official` — Example scripts under `/cm/local/examples/cmd/pythoncm` for automation.
  - Run: `module load python3 && python /cm/local/examples/cmd/pythoncm/status.py`
- **[Bright Cluster Installer Ansible Collection](https://github.com/Bright-Computing/bright-installer-ansible)** `Community` — Ansible collection and examples for deploying BCM head nodes.
  - Install: `ansible-galaxy collection install brightcomputing.installer100`
- **[BCM Ansible Playbooks](https://github.com/zeeace/BCM-Ansible)** `Community` — Community Ansible playbooks for NVIDIA Base Command Manager.
- **[CMDaemon REST API](https://docs.nvidia.com/base-command-manager/manuals/11/developer-manual.pdf)** `Official` — JSON REST interface for integrating external tools with BCM.
- **[Setting Up IBM Storage Scale with BCM](https://www.redbooks.ibm.com/docs/MD260011/MD260011.html)** `Community` — Reference guide for IBM Storage Scale integration with BCM clusters.

---

## Related Awesome Lists

- **[Awesome NVIDIA Agentic Skills and MCP Servers](../awesome-nvidia-agentic-skills-mcp)** — Agentic skills and MCP servers for NVIDIA products.
- **[Awesome GPU Cloud](../awesome-gpu-cloud)** — GPU cloud platforms and HPC cloud resources.
- **[Awesome MCP Servers](../awesome-mcp-servers)** — Model Context Protocol servers and integrations.
- **[Awesome Oracle Agentic Skills and MCP Servers](../awesome-oracle-agentic-skills-mcp)** — Agentic skills and MCP servers for Oracle Cloud and databases.

---

## Notes

- **Version numbering:** BCM versions follow a `MAJOR.YY.MM` pattern (e.g., 10.25.03, 11.25.08). Links point to the latest BCM 10/11 documentation where available; some deep sections still reference Bright Cluster Manager naming from before the NVIDIA rebrand.
- **Manual sections:** Many capabilities are documented as chapters in the Administrator, Installation, User, Containerization, and Developer manuals rather than as standalone web pages.
- **Community entries:** Community-maintained tools are listed for convenience; verify compatibility with your BCM version before use in production.
- **Updates welcome:** If you find a new BCM resource, see [CONTRIBUTING.md](./CONTRIBUTING.md) and open a pull request.

---

## Contributing

Read [CONTRIBUTING.md](./CONTRIBUTING.md) for the quality bar, entry format, and PR process.

---

## License

This list is released into the public domain under [CC0-1.0](./LICENSE).

## Want us to build this for you?

Enterprise AI Atlas is maintained by [Vibe Coding Agency](https://vibecodingagency.com). We prototype and ship agentic systems, MCP servers, and enterprise AI integrations for teams that need working software fast — without hiring a full AI engineering team.

**Free guide:** [The Non-Technical Founder's Guide to Agentic AI](https://vibecodingagency.com/resources/white-papers/non-technical-founders-guide-agentic-ai.pdf) — what agents and MCP servers are, and how to get a system built.
