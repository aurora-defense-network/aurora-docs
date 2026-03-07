# Installation

This document describes the intended installation model for Aurora components.

## Installation Approach

Aurora is being prepared for package-based Linux installation.

Planned packaging direction:

- Debian packages (`.deb`)
- systemd service integration
- configuration under `/etc/aurora`
- data under `/var/lib/aurora`
- logs under `/var/log/aurora`

## Components

### aurora-core
Primary control plane service.

### aurora-node-agent
Node-side service for participating infrastructure.

### aurora-simulator
Simulation and resilience testing tooling.

## Planned Service Model

Aurora services are expected to run as managed system services.

Example pattern:

```bash
sudo systemctl enable aurora-core
sudo systemctl start aurora-core
