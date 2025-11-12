## Objective
To implement infrastructure monitoring and centralized logging for the Jenkins server using AWS CloudWatch.

### Scope
- **Infrastructure Metrics:** CPU, memory, disk usage
- **Logs:** System logs, Jenkins logs / access logs
- **Dashboards:** Visual representation of server health and logs

---

## Step-by-Step Approach

### 1. Install CloudWatch Agent
- Installed AWS CloudWatch Agent on the EC2 instance.
- wget https://s3.amazonaws.com/amazoncloudwatch-agent/ubuntu/amd64/latest/amazon-cloudwatch-agent.deb
- sudo dpkg -i amazon-cloudwatch-agent.deb

### CloudWatch Agent Configuration

### Configuration File
`/home/ubuntu/cw-agent-config.json`

---

## Metrics Collected

### CPU
- `cpu_usage_idle`
- `cpu_usage_iowait`
- `cpu_usage_user`
- `cpu_usage_system`

### Memory
- `mem_used_percent`
- `mem_available_percent`

### Disk
- `used_percent` for `/`

---

## Logs Collected

### System Logs
- `/var/log/syslog` or `/var/log/messages`

### Jenkins Logs
- `/var/lib/jenkins/logs/*`

- **Log Groups**
  - `JenkinsServer/SystemLogs`
  - `JenkinsServer/JenkinsLogs`

- **Namespace**
  - `JenkinsServer`
 
### 3. Start CloudWatch Agent
- Commands Used:
  
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a start

### 4. Verification

- **Metrics:** Visible in **CloudWatch Metrics → JenkinsServer**  
- **Logs:** Visible in **CloudWatch Logs → JenkinsServer**  
- Confirm that system logs and Jenkins logs are being collected properly.

### 5. Dashboard Creation

**Infrastructure Dashboard**  
- Visualizes CPU, memory, and disk usage trends.

**Logs Dashboard**  
- Visualizes system logs and Jenkins logs for real-time monitoring.

### 6. Dashboard Screenshot

<img width="1366" height="768" alt="Screenshot (122)" src="https://github.com/user-attachments/assets/aef5526a-ffa4-4339-a208-6ed7616133bc" />




