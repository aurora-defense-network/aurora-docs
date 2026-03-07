# Aurora System Overview

Aurora consists of multiple cooperating components that together form a distributed defense network.

## Main Components

### Aurora Core
The control plane of the network.

Responsibilities include:

- node registration
- policy distribution
- routing decisions
- incident coordination
- trust evaluation
- certificate workflows

### Aurora Node Agent
Software that runs on participating nodes.

Responsibilities include:

- secure node enrollment
- telemetry reporting
- local policy enforcement
- certificate renewal
- local health reporting

### Aurora Simulator
A simulation and testing environment for validating behavior under load, failure and attack scenarios.

Responsibilities include:

- fake node generation
- traffic simulation
- incident simulation
- chaos and resilience testing

### Aurora Docs
The public documentation repository.

Responsibilities include:

- architecture overview
- operational guidance
- installation guidance
- governance documentation
- public documentation boundary

## Public Architecture View

Aurora can be understood as several logical layers:

- **Control Plane** – coordinates trust, policy and decisions
- **Telemetry Plane** – receives health and traffic-related signals
- **Routing Layer** – decides where traffic should be directed
- **Node Layer** – participating infrastructure nodes
- **Mitigation Layer** – applies protection behavior based on policy and incidents

## Trust Model

Aurora does not treat all nodes equally by default.
Nodes are expected to participate under explicit trust, policy and governance rules.

## Public Documentation Boundary

This documentation describes the public architecture and operational model.
Sensitive defensive details such as specific thresholds, internal infrastructure mapping
and certain mitigation internals are intentionally excluded from public documentation.
