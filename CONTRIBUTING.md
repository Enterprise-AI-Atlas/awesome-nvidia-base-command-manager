# Contributing

Contributions are welcome. Please read this guide before opening a pull request.

## What belongs in this list

This registry is for resources that help administrators and users deploy, operate, and optimize NVIDIA Base Command Manager (BCM) clusters. Acceptable entries include:

- Official NVIDIA BCM documentation, manuals, release notes, and training.
- BCM setup and provisioning tools (cmsh, cm-setup, cm-wlm-setup, cm-kubernetes-setup, cm-jupyter-setup, etc.).
- Workload manager guides and integrations for Slurm, PBS Professional, OpenPBS, and LSF on BCM.
- GPU configuration resources (MIG, CUDA MPS, DCGM, NVIDIA Container Toolkit) as used with BCM.
- Monitoring, observability, and diagnostic resources for BCM (Prometheus exporter, health checks, cm-diagnose).
- MPI, environment modules, and parallel computing resources on BCM.
- Container, Kubernetes, Cluster API, and Spark resources for BCM.
- Jupyter, JupyterHub, JupyterLab, and interactive app integrations on BCM.
- Community tools, automation, and scripts that extend or interact with BCM (Ansible, Python API, REST API).

## What does **not** belong

- Generic Linux or HPC resources that are not specifically applicable to BCM.
- General GPU, Slurm, or Kubernetes documentation unless it explicitly covers BCM integration.
- Closed-source or paywalled-only tools with no public documentation.
- Duplicate entries.

## Quality bar

Every submission must be:

1. **Publicly accessible** — open source or publicly documented.
2. **Actively maintained** — last meaningful update or relevant BCM version within the last 24 months (exceptions for official NVIDIA manuals).
3. **Documented** — a real README, manual section, or install/setup instructions.
4. **Correctly categorized** — placed under the BCM topic it primarily targets.
5. **Honestly labeled** — use the `Official` or `Community` badge.

## Entry format

Use this pattern:

```markdown
- **[Name](URL)** `Official` — One-sentence description.
  - Install: `command here`
```

If there is no install command, omit the install line.

## Product sections

The README is organized by **BCM functional area**, not by resource type. New sections are allowed only if they contain at least four entries.

## Pull request process

1. Fork the repository.
2. Add your entry in the correct functional section.
3. Run `./scripts/validate-links.sh` and fix any broken links or anchors.
4. Open a pull request with a clear description of the resource and why it fits.

One resource per pull request is preferred.
