# Jenkins Server Monitoring

## Overview
This repository contains the monitoring setup for the Jenkins server using **AWS CloudWatch**.  
It captures infrastructure metrics, system logs, and access logs, and provides dashboards for easy monitoring.

### Monitored Components
- **Infrastructure Metrics**
  - CPU usage
  - Memory usage
  - Disk usage
- **Logs**
  - System logs
  - Jenkins logs / access logs
- **Dashboards**
  - Infrastructure Metrics Dashboard
  - Logs Dashboard

---

## Prerequisites
- AWS account with necessary permissions for CloudWatch
- EC2 instance running Jenkins
- CloudWatch Agent installed on the instance
