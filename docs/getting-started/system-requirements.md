# System Requirements

This document describes the expected baseline system requirements for running Aurora components.

Aurora is designed to run on standard Linux infrastructure and scale from small test deployments to larger distributed environments.

> These requirements represent current development targets and may evolve as the system matures.

---

# Supported Platforms

Aurora is currently targeting Linux-based systems with a focus on:

- Debian 12
- Ubuntu 22.04 / 24.04
- systemd-based service environments

Other Linux distributions may work but are not currently tested.

---

# Aurora Components

Aurora consists of several components with different resource profiles.

- Aurora Core
- Aurora Node Agent
- Aurora Simulator

Each component has its own baseline requirements.

---

# Aurora Core

Aurora Core acts as the control plane of the Aurora defense network.

Responsibilities include:

- node registration
- policy distribution
- telemetry ingestion
- routing decisions
- incident coordination
- certificate workflows

### Minimum Requirements

| Resource | Minimum |
|--------|--------|
| CPU | 2 vCPU |
| RAM | 4 GB |
| Storage | 20 GB |
| Network | reliable connectivity |

### Recommended for Production

| Resource | Recommended |
|--------|--------|
| CPU | 4+ vCPU |
| RAM | 8+ GB |
| Storage | 50+ GB |
| Network | low-latency stable connection |

Additional capacity may be required depending on telemetry volume and node count.

---

# Aurora Node Agent

The Aurora Node Agent runs on infrastructure nodes participating in the Aurora network.

Responsibilities include:

- node enrollment
- telemetry reporting
- policy enforcement
- certificate renewal
- local health reporting

### Minimum Requirements

| Resource | Minimum |
|--------|--------|
| CPU | 1 vCPU |
| RAM | 2 GB |
| Storage | 10 GB |
| Network | outbound connectivity |

### Recommended

| Resource | Recommended |
|--------|--------|
| CPU | 2+ vCPU |
| RAM | 4+ GB |
| Storage | 20 GB |
| Network | stable high bandwidth |

The Node Agent is designed to run on a wide range of infrastructure systems.

---

# Aurora Simulator

The Aurora Simulator is used for testing, development and resilience validation.

Responsibilities include:

- simulated nodes
- simulated attack traffic
- routing behavior testing
- chaos and failure testing

### Minimum Requirements

| Resource | Minimum |
|--------|--------|
| CPU | 4 vCPU |
| RAM | 8 GB |
| Storage | 20 GB |

### Recommended for Large Simulations

| Resource | Recommended |
|--------|--------|
| CPU | 8+ vCPU |
| RAM | 16+ GB |
| Storage | 50+ GB |

Simulation resource usage scales with the number of simulated nodes and traffic volume.

---

# Network Requirements

Aurora components require basic network connectivity.

Typical requirements include:

- outbound HTTPS connectivity
- ability to reach Aurora services
- low-latency connections between distributed nodes

Exact network topology depends on deployment architecture.

---

# Operating System Environment

Aurora services are designed to run in a standard Linux service environment.

Typical system layout:


/etc/aurora configuration
/var/lib/aurora runtime data
/var/log/aurora logs
/usr/lib/aurora binaries


Aurora services are expected to be managed via `systemd`.

---

# Future Requirements

As Aurora evolves, additional requirements may emerge related to:

- telemetry scale
- detection workloads
- routing complexity
- mitigation capabilities
- observability stack integration

These will be documented as the system approaches production readiness.
