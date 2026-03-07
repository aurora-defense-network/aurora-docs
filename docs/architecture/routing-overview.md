# Routing Overview

This document describes the high-level routing model used by Aurora.

Aurora routing is designed to distribute traffic across multiple nodes in order to
reduce load concentration and improve resilience.

---

# Routing Goals

Aurora routing aims to achieve several goals:

- distribute traffic across available nodes
- avoid overloading individual nodes
- respond to node health signals
- support failover behavior
- improve network resilience

---

# Routing Inputs

Routing decisions may consider several inputs.

Examples include:

### Node Health

Nodes report health and operational status through telemetry.

Healthy nodes may receive more traffic than degraded nodes.

---

### Node Capacity

Nodes may advertise capabilities such as:

- bandwidth capacity
- compute capacity
- mitigation features

Routing may consider these capabilities.

---

### Geographic Region

Nodes may belong to geographic regions.

Routing decisions may prefer nodes closer to the traffic source
or within the same region.

---

### Trust Level

Nodes may have different trust levels depending on participation rules
and governance policies.

Routing may prefer nodes with higher trust levels.

---

### Policy Rules

Policies may influence routing behavior.

Examples:

- preferred regions
- restricted nodes
- mitigation routing behavior

---

# Routing Strategies

Aurora may implement several routing strategies.

Examples include:

### Weighted Distribution

Traffic may be distributed proportionally based on node capacity.

---

### Geo-Aware Routing

Traffic may be routed to nodes in the same region.

---

### Failover Routing

If a node becomes unavailable, traffic can be redirected to other nodes.

---

### Adaptive Routing

Routing decisions may adapt based on telemetry signals and incident conditions.

---

# Failure Handling

Aurora must respond to node failures or degraded conditions.

Possible actions include:

- temporarily removing nodes from routing
- reducing routing weight
- redirecting traffic to other regions

---

# Observability

Routing decisions may generate logs or metrics to help operators understand
why certain nodes were selected.

Examples:

- routing decision logs
- routing score evaluation
- routing trace information

These tools help operators debug routing behavior.

---

# Public Boundary

This document describes routing behavior at a conceptual level.

Detailed routing algorithms, thresholds and internal parameters are not part of
the public documentation.
