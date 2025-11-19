# Day 8 — Complete Cheat Sheets (Ultra-Fast Revision)

## Table of Contents
- [Networking Cheat Sheet](#net)
- [AWS Cheat Sheet](#aws)
- [Terraform Cheat Sheet](#tf)
- [Linux Admin Cheat Sheet](#linux)
- [Docker & Kubernetes Cheat Sheet](#k8s)
- [Security/SIEM/NDR/WAF Cheat Sheet](#sec)
- [Troubleshooting Quick Patterns](#troubleshoot)

---

# <a id="net"></a> Networking Cheat Sheet

## IP Classes
- A → 0.0.0.0 – 127.255.255.255 (/8)
- B → 128.0.0.0 – 191.255.255.255 (/16)
- C → 192.0.0.0 – 223.255.255.255 (/24)

## Common Subnet Masks
- /24 → 256 IPs → 254 hosts
- /25 → 128 IPs → 126 hosts
- /26 → 64 IPs → 62 hosts
- /27 → 32 IPs → 30 hosts
- /28 → 16 IPs → 14 hosts

## CIDR Math
- Hosts = 2^(32-mask) - 2
- Network = IP & Mask
- Broadcast = Last IP of block

## Ports
- SSH → 22
- HTTP → 80
- HTTPS → 443
- DNS → 53
- SMTP → 25
- SNMP → 161

---

# <a id="aws"></a> AWS Cheat Sheet

## VPC
- Public Subnet → IGW route 0.0.0.0/0
- Private Subnet → NAT route 0.0.0.0/0
- SG = stateful /
- NACL = stateless

## EC2
- ENI = virtual NIC
- Root device → EBS

## IAM
- User = human
- Role = AWS service permission
- Policy = JSON permissions

## S3
- SSE-S3 = AES-256
- SSE-KMS = KMS CMK keys

## Load Balancers
- ALB → L7
- NLB → L4
- GLB → global routing

---

# <a id="tf"></a> Terraform Cheat Sheet

## Basic Commands
```
terraform init
terraform plan
terraform apply
terraform destroy
```

## State Management
```
terraform state list
terraform state show <resource>
```

## Variables
```
variable "region" {
  default = "ap-south-1"
}
```

## Output
```
output "ip" {
  value = aws_instance.web.public_ip
}
```

---

# <a id="linux"></a> Linux Admin Cheat Sheet

## Important Commands
```
top / htop
journalctl -xe
systemctl status ssh
ss -tulnp
ip a
ip r
```

## File Permissions
- 755 = rwxr-xr-x
- 644 = rw-r--r--

## Logs
- /var/log/syslog
- /var/log/auth.log

## Processes
```
ps aux | grep nginx
kill -9 <pid>
```

---

# <a id="k8s"></a> Docker & Kubernetes Cheat Sheet

## Docker
```
docker ps
docker images
docker logs <id>
docker exec -it <id> bash
```

## Compose
```
docker-compose up -d
```

## Kubernetes Commands
```
kubectl get pods
kubectl describe pod <pod>
kubectl logs <pod>
kubectl apply -f file.yaml
```

## Common YAML Snippets
### Deployment
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: c1
        image: nginx
```

### Service
```
apiVersion: v1
kind: Service
spec:
  type: NodePort
  selector:
    app: myapp
  ports:
  - port: 80
    nodePort: 30080
```

---

# <a id="sec"></a> Security / SIEM / NDR / WAF Cheat Sheet

## SIEM Basics
- Log → Normalize → Correlate → Alert → Triage

## Common Use Cases
- Excessive failed logins
- Privilege escalation
- Suspicious outbound connections
- Port scanning detection

## Attack Types
- SQL Injection
- XSS
- DDoS
- Credential Stuffing

## WAF
Blocks:
- SQLi patterns
- Script tags
- Malicious URL

## NDR
Looks for:
- Beaconing
- Anomalous traffic
- Lateral movement
- Malware C2 patterns

---

# <a id="troubleshoot"></a> Troubleshooting Quick Patterns

## Linux Not Responding
- Check CPU: `top`
- Check memory: `free -h`
- Check logs: `journalctl -xe`

## Website Down
- Service: `systemctl status`
- Port: `ss -tulnp`
- Logs
- Nginx config syntax

## EC2 No Internet
- Wrong route table
- No IGW
- SG outbound blocked
- In private subnet without NAT

## Pod CrashLoop
- Check logs
- YAML errors
- Health probes

---
