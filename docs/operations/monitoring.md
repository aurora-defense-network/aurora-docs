# Monitoring

This document describes the basic monitoring model for Aurora components.

Aurora services expose operational endpoints and metrics that allow system administrators
to monitor service health, readiness and runtime behavior.

---

# Health Endpoints

Aurora services expose health endpoints that can be used for automated monitoring.

## Health Check

Endpoint:


/healthz


Purpose:

- indicates whether the service process is alive

Example:


curl http://localhost:8080/healthz


Example response:


status: ok


---

## Readiness Check

Endpoint:


/readyz


Purpose:

- indicates whether the service is fully initialized and ready to serve requests

Example:


curl http://localhost:8080/readyz


This endpoint is useful for:

- load balancers
- orchestration systems
- deployment validation

---

# Metrics Endpoint

Aurora services expose metrics for monitoring systems.

Endpoint:


/metrics


Metrics are designed to be compatible with monitoring systems such as:

- Prometheus
- Grafana
- other metrics collectors

Example:


curl http://localhost:8080/metrics


---

# Key Metrics

Examples of operational metrics include:

### Node Metrics


aurora_nodes_active
aurora_nodes_quarantined
aurora_nodes_degraded


### Incident Metrics


aurora_incidents_active
aurora_incidents_total


### Traffic Metrics


aurora_traffic_diverted
aurora_traffic_anomalies


### Performance Metrics


aurora_detection_latency
aurora_policy_distribution_latency


---

# Log Monitoring

Aurora services generate structured logs.

Typical log location:


/var/log/aurora/


Logs may include:

- service startup events
- node registration
- incident events
- policy changes
- certificate events

Logs should be integrated into a centralized logging system when running in production environments.

---

# Monitoring Strategy

Recommended monitoring approach:

1. monitor `/healthz`
2. monitor `/readyz`
3. collect `/metrics`
4. monitor service logs
5. alert on anomalies

---

# Production Observability

In larger deployments Aurora monitoring may include:

- Prometheus
- Grafana dashboards
- centralized log aggregation
- alerting systems such as Alertmanager

These tools help operators understand system behavior and detect problems early.
