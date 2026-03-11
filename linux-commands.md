# Linux Commands for DevOps Engineers

This document contains commonly used Linux commands with examples.
Useful for DevOps engineers during daily operations and troubleshooting.

---

# 1. System Information

## Check OS Information

```bash
uname -a
```

## Check CPU Information

```bash
lscpu
```

## Check Memory Usage

```bash
free -h
```

## Check Disk Space

```bash
df -h
```

## Check Disk Usage of Directory

```bash
du -sh /var/log
```

---

# 2. File and Directory Management

## List Files

```bash
ls
```

## List Files with Details

```bash
ls -la
```

## Create Directory

```bash
mkdir project
```

## Create Nested Directory

```bash
mkdir -p project/app/config
```

## Remove File

```bash
rm file.txt
```

## Remove Directory

```bash
rm -r directory_name
```

## Copy File

```bash
cp file1.txt file2.txt
```

## Move or Rename File

```bash
mv oldname.txt newname.txt
```

---

# 3. File Viewing Commands

## View File Content

```bash
cat file.txt
```

## View First 10 Lines

```bash
head file.txt
```

## View Last 10 Lines

```bash
tail file.txt
```

## Monitor Logs in Real Time

```bash
tail -f /var/log/messages
```

---

# 4. Searching

## Search Text in File

```bash
grep "error" logfile.log
```

## Search File in Directory

```bash
find /home -name file.txt
```

## Locate File Quickly

```bash
locate file.txt
```

---

# 5. File Permissions

## View File Permissions

```bash
ls -l
```

## Change File Permissions

```bash
chmod 755 script.sh
```

## Change File Owner

```bash
chown ec2-user file.txt
```

---

# 6. Process Management

## View Running Processes

```bash
ps -ef
```

## Monitor System Processes

```bash
top
```

## Kill Process

```bash
kill <PID>
```

## Force Kill Process

```bash
kill -9 <PID>
```

---

# 7. Networking

## Check IP Address

```bash
ip a
```

## Check Network Connectivity

```bash
ping google.com
```

## Check Open Ports

```bash
netstat -tulnp
```

## Test HTTP Request

```bash
curl http://example.com
```

---

# 8. Package Management (Amazon Linux / RHEL)

## Update Packages

```bash
sudo yum update -y
```

## Install Package

```bash
sudo yum install docker -y
```

## Remove Package

```bash
sudo yum remove docker
```

---

# 9. Service Management

## Check Service Status

```bash
systemctl status docker
```

## Start Service

```bash
sudo systemctl start docker
```

## Enable Service at Boot

```bash
sudo systemctl enable docker
```

## Restart Service

```bash
sudo systemctl restart docker
```

---

# 10. Useful DevOps Commands

## Check Docker Containers

```bash
docker ps
```

## Check Kubernetes Pods

```bash
kubectl get pods
```

## Check AWS CLI Version

```bash
aws --version
```

---

# Conclusion

These commands are commonly used by DevOps engineers for:

* System troubleshooting
* Log monitoring
* File management
* Networking checks
* Process control
* Service management

Maintaining command documentation helps improve operational efficiency and troubleshooting speed.
