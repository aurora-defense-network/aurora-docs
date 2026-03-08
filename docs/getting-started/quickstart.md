# Aurora Quickstart

This quickstart provides a high-level path for setting up Aurora components.

> Aurora is currently under active development. Exact installation steps may evolve.

## Intended Basic Flow

1. Install the Aurora component you need  
2. Configure the service  
3. Start the service  
4. Verify health and readiness  
5. Connect the component to the Aurora environment  

---

## Core Service Example

Expected flow:

```bash
sudo apt update
sudo apt install aurora-core
sudo systemctl enable aurora-core
sudo systemctl start aurora-core
```

### Verify Status

```bash
curl http://localhost:<aurora-port>/healthz
curl http://localhost:<aurora-port>/readyz
```

For local testing the service may expose HTTP on localhost.
Production deployments typically use HTTPS with Aurora's PKI and mTLS configuration.

---

## Node Agent Example

Expected flow:

```bash
sudo apt install aurora-node-agent
sudo systemctl enable aurora-node-agent
sudo systemctl start aurora-node-agent
```

---

## Notes

This quickstart intentionally stays high level.

Detailed installation, configuration and production hardening guidance belongs in the operations documentation.

---

# System Requirements

**File location**

```
docs/getting-started/system-requirements.md
```

---

# System Requirements

This document describes the expected baseline requirements for Aurora components.

Aurora is designed to run on standard Linux infrastructure and scale from small test deployments to larger distributed environments.

These requirements represent current development targets and may evolve as the system matures.

---

## Supported Platforms

Aurora is currently targeting Linux-based deployment environments with a focus on:

- Debian 12
- Ubuntu 22.04
- Ubuntu 24.04
- systemd-based service environments

Other Linux distributions may work but are not currently tested.

---

# Aurora Components

Aurora consists of several components with different resource profiles.

Main components include:

- **Aurora Core**
- **Aurora Node Agent**
- **Aurora Simulator**

Each component has its own baseline requirements.

---

# Aurora Core

Aurora Core acts as the **control plane** of the Aurora defense network.

Responsibilities include:

- node registration
- policy distribution
- telemetry ingestion
- routing decisions
- incident coordination
- certificate workflows

### Minimum Requirements

| Resource | Minimum |
|---------|---------|
| CPU | 2 vCPU |
| RAM | 4 GB |
| Storage | 20 GB |
| Network | reliable connectivity |

Aurora Core expects a **systemd-based Linux service environment**.

---

### Recommended for Production

| Resource | Recommended |
|---------|-------------|
| CPU | 4+ vCPU |
| RAM | 8+ GB |
| Storage | 50+ GB |
| Network | low-latency stable connection |

Additional capacity may be required depending on:

- telemetry volume
- node count
- mitigation workload
- routing decision rate

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
|---------|---------|
| CPU | 1 vCPU |
| RAM | 2 GB |
| Storage | 10 GB |
| Network | outbound connectivity |

The Node Agent requires:

- outbound connectivity to Aurora services
- certificate storage capability
- systemd service support

---

### Recommended

| Resource | Recommended |
|---------|-------------|
| CPU | 2+ vCPU |
| RAM | 4+ GB |
| Storage | 20 GB |
| Network | stable high bandwidth |

The Node Agent is designed to run on a wide range of infrastructure systems.

---

# Aurora Simulator

The Aurora Simulator is used for:

- testing
- development
- resilience validation
- chaos and failure testing

Responsibilities include:

- simulated nodes
- simulated attack traffic
- routing behavior testing
- chaos scenarios

### Minimum Requirements

| Resource | Minimum |
|---------|---------|
| CPU | 4 vCPU |
| RAM | 8 GB |
| Storage | 20 GB |

---

### Recommended for Large Simulations

| Resource | Recommended |
|---------|-------------|
| CPU | 8+ vCPU |
| RAM | 16+ GB |
| Storage | 50+ GB |

Simulation resource usage scales with:

- number of simulated nodes
- traffic volume
- complexity of scenarios

---

# Network Requirements

Aurora components require basic network connectivity.

Typical requirements include:

- outbound HTTPS connectivity
- ability to reach Aurora services
- low-latency connections between distributed nodes

Exact network topology depends on the deployment architecture.

---

# Operating System Environment

Aurora services are designed to run in a standard Linux service environment.

Typical filesystem layout:

```
/etc/aurora      configuration
/var/lib/aurora  runtime data
/var/log/aurora  logs
/usr/lib/aurora  binaries
```

Aurora services are expected to be managed using **systemd**.

---

# Future Requirements

As Aurora evolves, additional requirements may emerge related to:

- telemetry scale
- detection workloads
- routing complexity
- mitigation capabilities
- observability stack integration

These requirements will be documented as the system approaches production readiness.

