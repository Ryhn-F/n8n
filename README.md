# 🚀 n8n Deployment on AWS EC2 with Supabase DB

This repository provides a step-by-step guide to deploying **n8n** from your GitHub repo onto an **AWS EC2 instance**, using **Supabase Postgres** as the database for persistent workflow storage.

---

## 🔹 Prerequisites
- AWS account with EC2 access
- Supabase account (free tier works fine)
- GitHub repo containing your n8n `Dockerfile`
- SSH key (`.pem`) for connecting to EC2
- Basic knowledge of Docker and Linux

---

## 🔹 Step 1 — Launch AWS EC2
1. Go to [AWS EC2 Console](https://console.aws.amazon.com/ec2/).
2. Launch an **Ubuntu 22.04 LTS** instance (`t2.micro` is free-tier eligible).
3. Configure **Security Group** to allow:
   - `22` → SSH
   - `80` → HTTP
   - `443` → HTTPS
   - `5678` → n8n editor (optional if not behind reverse proxy)
4. Download the **key pair** (`.pem`) for SSH access.

---

## 🔹 Step 2 — Connect to EC2
```bash
ssh -i your-key.pem ubuntu@<ec2-public-ip>
