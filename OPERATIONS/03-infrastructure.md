# Infrastructure

---

## 🏗️ Current State (2025)

**Hosting :** Oumorou's personal VPS (Hetzner or similar)  
**Status :** Simple setup, manual deployment  
**Plan :** Upgrade to professional setup as company grows  

---

## 🎯 Infrastructure Roadmap

### Phase 1A (Q1 2025)
- Separate Bouringa infrastructure from personal
- Basic VPS setup (Ubuntu 24)
- Manual deployments (SSH + bash scripts)
- Cost: $10-20/month

### Phase 1B (Q3 2025)
- Docker containerization
- Docker Compose for deployments
- Automated backups
- Cost: $20-40/month

### Phase 1C (2026)
- CI/CD pipeline (GitHub Actions or GitLab CI)
- Monitoring & alerting setup
- Database auto-backups
- Cost: $40-60/month

### Phase 2 (2027+)
- Kubernetes (k3s) for larger projects
- Multi-environment setup (dev/staging/prod)
- Load balancing if needed
- Cost: $100-200/month+

---

## 💻 Server Setup (Phase 1B)

### Primary VPS Specs (Recommended)

| Spec | Requirement |
|------|-------------|
| CPU | 4 cores minimum |
| RAM | 8GB minimum |
| Storage | 100GB SSD |
| Bandwidth | 1TB+ monthly |
| OS | Ubuntu 24 LTS |
| Provider | Hetzner, DigitalOcean, AWS |

### Cost Estimate
- Hetzner : $10-15/month
- DigitalOcean : $15-20/month
- AWS EC2 : $20-40/month (more variable)

### Server Configuration

```
/srv/bouringa/
├── apps/                  # Docker containers
│   ├── app-1/
│   ├── app-2/
│   └── docker-compose.yml
├── data/                  # Databases
│   └── postgres/
├── backups/               # Daily backups
├── nginx/                 # Reverse proxy config
└── monitoring/            # Prometheus, Grafana
```

---

## 🐳 Containerization (Docker)

### Docker Compose Example

```yaml
version: '3.8'
services:
  app:
    image: bouringa/app:latest
    ports:
      - "8080:8080"
    environment:
      - DB_URL=postgres://db:5432/myapp
    depends_on:
      - db
  
  db:
    image: postgres:15
    environment:
      - POSTGRES_PASSWORD=secure_password
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  postgres_data:
```

### Deployment Flow

```
1. Developer pushes code to main branch
2. GitHub/GitLab CI runs tests
3. Docker image built
4. Image pushed to registry
5. Server pulls latest image
6. Docker Compose restart
7. Health check runs
8. Client notified of deployment
```

---

## 🔐 Security Hardening

### OS Level
- [ ] SSH key auth only (no passwords)
- [ ] Firewall rules (UFW)
- [ ] Fail2ban for intrusion detection
- [ ] Auto-updates enabled
- [ ] Regular security audits

### Application Level
- [ ] HTTPS only (Let's Encrypt)
- [ ] Strong database passwords
- [ ] Secrets management (not in code)
- [ ] Input validation & sanitization
- [ ] SQL injection prevention

### Backup & Disaster Recovery
- [ ] Daily database backups
- [ ] Off-site backup storage
- [ ] Tested restore procedures
- [ ] RTO (Recovery Time Objective) : 4 hours
- [ ] RPO (Recovery Point Objective) : 24 hours

---

## 📊 Monitoring & Alerting

### Key Metrics to Monitor
- [ ] CPU usage (alert if >80%)
- [ ] Memory usage (alert if >85%)
- [ ] Disk usage (alert if >90%)
- [ ] Network bandwidth
- [ ] Application uptime
- [ ] Response times
- [ ] Error rates
- [ ] Database query time

### Monitoring Stack
- **Prometheus** : Collect metrics
- **Grafana** : Visualize metrics
- **Alertmanager** : Send alerts (Slack, email)

### Alert Channels
- Slack (primary, immediate)
- Email (backup, logs kept)
- SMS (for critical issues, later)

---

## 🔄 Deployment Process

### Pre-Deployment Checklist
- [ ] All tests pass
- [ ] Code review completed
- [ ] Changelog updated
- [ ] Database migrations tested (if needed)
- [ ] Secrets configured on server
- [ ] Rollback plan ready

### Deployment Steps
1. Backup current database
2. Pull latest code
3. Run database migrations (if any)
4. Build Docker image
5. Run health checks
6. Deploy new image
7. Monitor for errors (30 min)
8. Notify client

### Rollback Procedure (If Needed)
1. Revert to previous Docker image
2. Restore database from backup (if data change)
3. Run tests
4. Notify client

---

## 📈 Scaling Strategy

### Small Scale (Current / Phase 1)
- Single VPS
- Docker Compose for simplicity
- Manual or GitHub Actions for CI/CD
- Sufficient for <100 users

### Medium Scale (Phase 2)
- Multiple VPS (app + database separated)
- Load balancer
- Redis for caching
- Kubernetes (k3s) for orchestration
- Sufficient for 100-10K users

### Large Scale (Phase 3+)
- Managed cloud (AWS, GCP, Azure)
- Auto-scaling groups
- CDN for static assets
- Database replication
- Serverless functions (if applicable)

---

## 💰 Infrastructure Cost Breakdown (Phase 1-2)

| Component | Cost/Month | Notes |
|-----------|-----------|-------|
| VPS | $20-50 | Depends on provider |
| Database | $0 (in VPS) | Or separate $10-20 |
| Backups | $5-10 | Cloud storage |
| Monitoring | $0 (OSS) | Or $20+ for paid SaaS |
| DNS | $5-10 | If custom domain |
| **Total** | **$30-100** | Scalable with business |

---

**Last Updated:** January 2025  
**Infrastructure Review :** Q2 2025
