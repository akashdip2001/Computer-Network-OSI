# Day 7 — Final Interview Prep: Mock Interview, 150 Questions, HR Answers & Scenarios

## Table of Contents
- [Technical Mock Interview (Full Simulation)](#mock)
- [150 Technical Questions (Cloud, DevOps, Networking, Security)](#questions)
- [Behavioral + HR Round Answers](#hr)
- [Real-World Troubleshooting Scenarios](#scenarios)
- [Resume Talking Points](#resume)
- [Final 1-Week Revision Strategy](#revision)

---

# <a id="mock"></a> Technical Mock Interview (Simulation)
Use this section to practice.

### ❓ Q1: Explain VPC architecture in AWS.
**Answer:** A VPC is an isolated network with subnets (public/private), route tables, security groups, NACLs, and gateways (IGW/NAT). Public subnets route 0.0.0.0/0 to IGW, private route to NAT.

### ❓ Q2: How does Terraform work internally?
**Answer:** Terraform uses providers to map API resources, stores state in tfstate, plans execution with DAG graph, and applies changes via CRUD actions.

### ❓ Q3: How does DNS resolution work?
**Answer:** Client → Resolver → Root → TLD → Authoritative → IP returned → cached.

### ❓ Q4: How do you troubleshoot high CPU on Linux?
**Answer:** Use `top`, `htop`, `ps aux --sort=-%cpu`, check logs, kill process, analyze using `journalctl`.

### ❓ Q5: Explain Docker architecture.
**Answer:** Docker CLI → Docker Engine → Daemon → Images/Containers layered filesystem (AUFS/OverlayFS).

### ❓ Q6: In Kubernetes, how does a service discover pods?
**Answer:** Through labels + selectors. kube-proxy programs iptables/ipvs rules.

### ❓ Q7: Difference between Security Groups and NACL?
**Answer:** SG = stateful, attached to ENI. NACL = stateless, attached to subnet.

### ❓ Q8: How do you detect port scanning in SIEM?
**Answer:** Multiple connection attempts on sequential ports + unusual patterns.

### ❓ Q9: What is the difference between ALB and NLB?
**Answer:** ALB L7 routing; NLB L4, ultra-fast performance.

### ❓ Q10: Troubleshoot: EC2 unable to access internet.
- No IGW?
- Wrong route table?
- SG outbound blocked?
- NACL reject?
- Instance in private subnet without NAT?

---

# <a id="questions"></a> 150 Technical Questions

## AWS (30)
1. What is a VPC CIDR limit?
2. Difference between SG inbound vs outbound?
3. NAT Gateway vs NAT Instance?
4. S3 consistency model?
5. IAM Role vs User vs Policy?
...

## Networking (30)
1. Explain TCP 3-way handshake.
2. ARP vs RARP.
3. Subnetting: /28 network size?
4. What is MTU?
5. VLAN vs Subnet?
...

## Linux (30)
1. What is SELinux enforcing?
2. `journalctl -u sshd` meaning?
3. Hard link vs soft link?
4. What is cgroups?
5. How to trace open ports?
...

## Docker/Kubernetes (30)
1. Pod vs Container.
2. ReplicaSet purpose.
3. NodePort range.
4. ConfigMap vs Secret.
5. Docker COPY vs ADD.
...

## Security/SOC (30)
1. What is MITRE ATT&CK?
2. SIEM parsing vs correlation.
3. IOC vs IOA.
4. WAF detection for SQLi.
5. Brute force indicators.
...

---

# <a id="hr"></a> HR Round + Behavioral Answers

### Q1: Tell me about yourself.
A crisp answer linking Mechanical → Cloud/DevOps → Security.

### Q2: Why should we hire you?
Because you combine networking + cloud + DevOps + security, making you highly versatile.

### Q3: Why do you want this job?
To build scalable infrastructure, automate environments, and work in deep technical problem-solving.

### Q4: What is your strength?
Fast learning, strong fundamentals, problem-solving.

### Q5: Weakness?
“I go deeply into topics; now I manage it with timeboxing.”

### Q6: Salary expectation?
“Based on my skills, 10 LPA is fair, but open to discussion.”

### Q7: Are you willing to relocate?
“Yes, if required for the role's success.”

---

# <a id="scenarios"></a> Real-World Troubleshooting Scenarios

### Scenario 1: Website down
- Check Nginx/Apache
- `ss -tulnp`
- DNS resolution
- Firewall
- Logs: `journalctl -u`

### Scenario 2: High memory usage
- `free -m`
- `top`
- Check swap
- Identify leak

### Scenario 3: Pod CrashLoopBackOff
- Check logs: `kubectl logs`
- Read events
- YAML errors
- Liveness probes

### Scenario 4: VPN not connecting
- Check routes
- Check iptables
- Check DNS leaks

### Scenario 5: SIEM false positives
- Adjust correlation
- Tune rules
- Whitelisting

---

# <a id="resume"></a> Resume Talking Points
- Docker + Terraform + Linux hands-on
- AWS/GCP/IAM/VPC knowledge
- Packet analysis (Nmap/Wireshark)
- Automation mindset
- Infrastructure design understanding

---

# <a id="revision"></a> Final 1-Week Revision Strategy

## Day 1: Networking + Subnetting
## Day 2: Linux + Logs + Services
## Day 3: AWS (VPC/EC2/S3/IAM)
## Day 4: Docker + Kubernetes
## Day 5: Terraform + CI/CD
## Day 6: SIEM + Security
## Day 7: Mock Interview + HR Prep

---