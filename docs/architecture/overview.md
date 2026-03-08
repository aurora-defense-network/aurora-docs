# Aurora Architecture Overview

Aurora is designed as a distributed defense network consisting of several cooperating components.

The system is built around a control plane and multiple infrastructure nodes participating in the Aurora network.

## Core Components

Aurora currently consists of the following primary components:

- **Aurora Core**
- **Aurora Node Agent**
- **Aurora Simulator**

Each component fulfills a specific role in the system.

## Aurora Core

Aurora Core acts as the central control plane.

Responsibilities include:

- node registration
- policy distribution
- telemetry ingestion
- routing decision making
- incident coordination
- certificate lifecycle management

## Aurora Node Agent

The Node Agent runs on participating infrastructure nodes.

Responsibilities include:

- telemetry reporting
- policy enforcement
- mitigation execution
- local health monitoring
- certificate renewal

## Aurora Simulator

The Aurora Simulator is used for testing and resilience validation.

It allows simulation of:

- node networks
- attack traffic
- routing behavior
- failure scenarios

## Architectural Principles

Aurora follows several design principles:

- distributed defense architecture
- failure-domain aware routing
- strong identity and trust model
- plane separation (control, telemetry, data)
- operator-focused observability

Further architectural documentation will be added as the system evolves.
