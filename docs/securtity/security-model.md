# Aurora Security Model

Aurora is designed as a security-sensitive infrastructure system.

Several principles guide the security architecture.

## Identity and Trust

All Aurora nodes use cryptographic identity.

Certificates are used to establish trust between components.

## Plane Separation

Aurora separates several communication planes:

- control plane
- telemetry plane
- data plane

Each plane has its own security controls.

## Certificate Infrastructure

Aurora uses an internal PKI model.

Certificates are used for:

- node authentication
- service identity
- secure communication

Further details will be documented as the PKI implementation evolves.
