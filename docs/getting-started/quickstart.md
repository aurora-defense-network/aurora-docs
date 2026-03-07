Quickstart für späteren Betrieb
docs/getting-started/quickstart.md
# Aurora Quickstart

This quickstart provides a high-level path for setting up Aurora components.

> Aurora is currently under active development. Exact installation steps may evolve.

## Intended Basic Flow

1. Install the Aurora component you need
2. Configure the service
3. Start the service
4. Verify health and readiness
5. Connect the component to the Aurora environment

## Core Service Example

Expected flow:

```bash
sudo apt update
sudo apt install aurora-core
sudo systemctl enable aurora-core
sudo systemctl start aurora-core
Verify Status
curl http://localhost:8080/healthz
curl http://localhost:8080/readyz
Node Agent Example

Expected flow:

sudo apt install aurora-node-agent
sudo systemctl enable aurora-node-agent
sudo systemctl start aurora-node-agent
Notes

This quickstart intentionally stays high level.
Detailed installation, configuration and production hardening guidance belongs in the operations documentation.


---

# Systemanforderungen

## `docs/getting-started/system-requirements.md`

```markdown
# System Requirements

This document describes the expected baseline requirements for Aurora components.

## Supported Platform Direction

Aurora is currently targeting Linux-based deployment environments, with a focus on:

- Debian 12
- Ubuntu 22.04 / 24.04

## Aurora Core

Preliminary baseline:

- 2 vCPU minimum
- 4 GB RAM minimum
- 20 GB storage
- reliable network connectivity
- systemd-based service environment

## Aurora Node Agent

Preliminary baseline:

- 1-2 vCPU
- 2 GB RAM minimum
- local outbound connectivity to Aurora services
- certificate storage capability
- systemd-based service environment

## Simulator

Preliminary baseline:

- depends on simulation scale
- recommended: 4+ vCPU
- recommended: 8+ GB RAM for larger test runs

## Notes

Production sizing depends on:

- node count
- telemetry volume
- routing decision rate
- mitigation complexity
- observability stack size
