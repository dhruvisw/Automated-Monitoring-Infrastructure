# Task: Automated Monitoring of Infrastructure with Prometheus

## Overview of the Concept

This task demonstrates the creation of an automated infrastructure monitoring environment
using Prometheus. The monitoring setup is implemented following the Infrastructure as Code
(IaC) paradigm and is provisioned, executed, and validated using an automated CI/CD pipeline.

Detached target servers named `demo-target-1` and `demo-target-2` expose operational metrics via HTTP on ports `9100` and `9200`. A separate monitoring server running Prometheus periodically
scrapes metrics from the target servers every `5` seconds using a pull-based monitoring model.

Both the target server and the monitoring server are provisioned automatically using
containerised virtualisation based on Ubuntu 24.04. The entire setup is integrated into
a single CI/CD workflow, allowing future configuration changes to be applied without
manual intervention.

A separate automated test verifies that the monitoring server successfully collects
the expected metrics from the target server.

## Configuration Example

- Target server name: `demo-target`
- Metrics port: `9100`
- Prometheus scrape interval: `5s`
