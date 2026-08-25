<p align="center">
  <img src="https://img.shields.io/badge/status-production%20ready-brightgreen" alt="Status">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License">
  <img src="https://img.shields.io/badge/OWASP%20Top%2010-covered-success" alt="OWASP">
  <img src="https://img.shields.io/badge/TypeScript-5.3-3178C6" alt="TypeScript">
</p>

<h1 align="center">🛡️ FireWAF — Self-Hosted Web Application Firewall</h1>

<p align="center">
  A production-grade, self-hosted reverse-proxy Web Application Firewall (WAF)
  with OWASP CRS-style detection, anomaly scoring, rate limiting, and an admin dashboard.
  <br />
  <strong>Detects and blocks:</strong> SQLi, XSS, Command Injection, LFI, SSRF, XXE, and more.
</p>

---

## ✨ Features

- **Reverse Proxy** — sits transparently between client and backend, forwards clean traffic
- **OWASP CRS-Style Detection Engine** — 30+ rules covering OWASP Top 10
- **Anomaly Scoring** — ModSecurity-style: multiple low-severity matches accumulate to block, reducing false positives
- **Input Normalization** — URL-decode, HTML-entity decode, Unicode NFKC, null-byte stripping — stops encoding evasion
- **Rate Limiting** — per-IP sliding window (Redis-backed), auto temporary bans
- **IP Allow/Deny** — static CIDR-based allowlist and denylist
- **Structured JSON Logging** — every request logged with full details
- **Monitor Mode** — log but don't block, great for tuning rules
- **Admin Dashboard** — React web UI with live traffic, stats, rule management, IP management
- **Docker Compose** — one command to spin up WAF + backend + Redis + PostgreSQL
- **Horizontal Scalability** — shared Redis state for multi-instance deployments

## 📋 Table of Contents

- [Quick Start (Linux)](#quick-start-linux)
- [Quick Start (Windows)](#quick-start-windows)
- [Manual Setup (No Docker)](#manual-setup-no-docker)
- [Architecture](#architecture)
- [Configuration](#configuration)
- [Rule Writing Guide](#rule-writing-guide)
- [API Reference](#api-reference)
- [Testing Guide](#testing-guide)
- [Production Deployment](#production-deployment)
- [Contributing](#contributing)
- [License](#license)

---

## 🐧 Quick Start (Linux)

### Prerequisites
- Docker Engine 24+ and Docker Compose v2+
- Git

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/firewaf.git
cd firewaf

# 2. Start all services
docker compose up --build -d

# 3. Verify everything is running
docker compose ps

# 4. Open the WAF-protected app
curl http://localhost:8080

# 5. Login to the admin dashboard
#    URL: http://localhost:3000
#    Username: admin
#    Password: admin123!  (CHANGE IMMEDIATELY)



File	Purpose
README.md	Main project documentation — setup, usage, architecture, API, testing
CONTRIBUTING.md	Guide for contributors
LICENSE	MIT license
.gitignore	Prevents committing unnecessary files
The README covers both Linux and Windows in detail, including:

Docker-based setup (recommended, works identically on both)
Manual setup without Docker
Platform-specific troubleshooting for Windows
Full API reference
Complete testing guide with curl commands for both bash and PowerShell
Production deployment checklist
