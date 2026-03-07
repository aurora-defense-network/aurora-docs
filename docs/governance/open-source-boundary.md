# Open Source Boundary

Aurora aims to be transparent where transparency improves trust, interoperability and reviewability.

At the same time, Aurora intentionally limits publication of certain operational security details.

## Public by Default

The following areas are suitable for public documentation:

- architecture overview
- installation guidance
- operational baseline guidance
- governance rules
- trust model at a high level
- public APIs where appropriate
- component responsibilities

## Not Public

The following areas should not be published in full detail:

- private keys
- certificate authority secrets
- internal credentials
- real infrastructure topology
- internal node inventories
- sensitive routing internals
- exact mitigation thresholds
- detection tuning parameters
- internal response playbooks
- privileged operational procedures

## Principle

Aurora should not rely on secrecy of the overall design for security.
However, it must protect secrets, sensitive operational detail and abuse-enabling internals.

## Goal

The purpose of this boundary is to balance:

- openness
- trust
- auditability
- resilience
- abuse resistance
