# Automated Infrastructure Monitoring with Prometheus

This exercise describes the automated creation of an infrastructure monitoring
system based on Infrastructure as Code (IaC) principles. The monitoring setup
consists of detached Linux-based servers and a dedicated monitoring service that
operate independently from one another.

Each monitored server exposes operational metrics via an HTTP endpoint. A
Prometheus monitoring service periodically retrieves these metrics using a
pull-based monitoring model. The monitoring service and the monitored servers
communicate exclusively over the network and are not co-located within the same
execution context.

All infrastructure components are provisioned and managed automatically and are
designed to operate within resource-restricted environments. Configuration
parameters are externalized using variables, allowing the monitoring topology and
behavior to be modified without changing the underlying automation logic.

The monitoring setup is designed to function autonomously and to support
automatic verification of correct behavior after provisioning. This ensures that
the monitored infrastructure can be validated deterministically without manual
interaction.

The exercise is executed on Ubuntu 24.04 and uses container-based virtualization
to simulate detached servers and network communication between infrastructure
components.

Prometheus dynamically discovers and scrapes the configured target servers based
on the selected variable values. Modifying these values results in different
monitoring topologies and runtime behaviors while preserving the same automated
provisioning and validation mechanisms.

---

# Variables

## `{TARGET_NAME}`
- Logical identifier used to name monitored target servers
- Used for service naming and network identification
- Allows multiple independent target instances to be created

**Possible values:**
- `demo-target`
- `app-node`

---

## `{TARGET_PORT}`
- TCP port on which a target server exposes its HTTP metrics endpoint
- Must be reachable from the monitoring server
- Determines how Prometheus connects to the monitored service

**Possible values:**
- `8000`
- `9100`
- `9200`

---

## `{SCRAPE_INTERVAL}`
- Interval at which Prometheus scrapes metrics from the target servers
- Represents a trade-off between monitoring resolution and system overhead

**Possible values:**
- `1s`
- `5s`
