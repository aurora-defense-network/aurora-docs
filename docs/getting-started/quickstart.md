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
