# Cybersecurity Platform Docker Compose

This repository deploys a full **Cybersecurity Stack** using Docker Compose:

- **TheHive** - Security Incident Response Platform
- **Cortex** - Analysis engine for TheHive
- **Wazuh** - Security monitoring and SIEM
- **MISP** - Malware Information Sharing Platform

All services are accessible via **Nginx reverse proxy** with HTTPS (self-signed for testing).

---

## Features

- Automatic Docker network creation (`cicd-net`)
- Persistent volumes for all services
- Reverse proxy with Nginx
- Self-signed SSL certificates for local testing
- GitHub Actions workflow to automatically deploy on push

---

## Requirements

- Docker & Docker Compose installed
- GitHub Actions enabled (for automated CI/CD)
- `/etc/hosts` entries for local testing:

