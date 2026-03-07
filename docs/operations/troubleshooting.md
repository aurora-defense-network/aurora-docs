# Troubleshooting

This document describes common troubleshooting steps for Aurora components.

---

# Service Not Starting

If the Aurora service does not start, first check the system service status.

Example:


sudo systemctl status aurora-core


Check service logs:


journalctl -u aurora-core


Common causes include:

- configuration errors
- missing permissions
- port conflicts
- invalid environment variables

---

# Health Check Failing

If `/healthz` fails:


curl http://localhost:8080/healthz


Possible causes:

- service crash
- resource exhaustion
- configuration issues

Check logs for startup errors.

---

# Readiness Check Failing

If `/readyz` fails, the service may still be initializing.

Possible causes:

- database initialization
- telemetry subsystem startup
- certificate loading
- policy initialization

Wait for initialization to complete and check logs.

---

# Node Registration Issues

If a node cannot register with Aurora Core:

Check:

- network connectivity
- certificate validity
- configuration settings
- system time synchronization

Time synchronization is important for certificate validation.

---

# Certificate Issues

Certificate-related errors may occur if:

- certificates expired
- renewal failed
- clock skew between systems

Verify:


date


Ensure system clocks are synchronized using NTP or similar services.

---

# High CPU or Memory Usage

Possible causes:

- large telemetry ingestion
- heavy simulation workloads
- large node networks

Check running processes:


top


or


htop


Investigate logs for abnormal activity.

---

# Logs

Aurora logs are typically located at:


/var/log/aurora/


Important log categories may include:

- startup logs
- telemetry logs
- incident logs
- certificate logs

---

# When to Escalate

If problems cannot be resolved using the steps above:

- review service configuration
- review recent updates
- inspect logs for anomalies
- consult Aurora documentation
