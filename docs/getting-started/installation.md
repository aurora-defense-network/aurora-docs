# Aurora Installation

Aurora components are distributed as Linux packages.

Currently supported platforms:

- Debian 12
- Ubuntu 22.04
- Ubuntu 24.04

Aurora packages can be installed using the system package manager.

Example:

```bash
sudo apt update
sudo apt install aurora-core

After installation the Aurora service can be started using systemd.

sudo systemctl enable aurora-core
sudo systemctl start aurora-core

Further installation guides will be added as Aurora approaches production readiness.


---

# 3. Configuration Overview

Neue Datei:


docs/configuration/configuration-overview.md


Beispiel:

```markdown
# Aurora Configuration Overview

Aurora configuration files are stored under:


/etc/aurora


Typical configuration files include:

- core configuration
- node agent configuration
- routing configuration
- telemetry configuration

Aurora may prompt the system administrator for important parameters during installation, such as:

- service ports
- network bindings
- certificate locations

Default values are intentionally conservative to ensure compatibility with a wide range of systems.

Detailed configuration documentation will be added as Aurora evolves.
