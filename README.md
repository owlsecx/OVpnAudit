# 🦉 OVpnAudit

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OVpnAudit** — VPN Configuration Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OVpnAudit is an offline, read-only VPN server configuration auditor for OpenVPN and WireGuard that parses .conf/.ovpn files and server directives with stdlib-only parsers. It evaluates cipher and TLS strength, authentication and certificate settings, key/secret file permissions, and insecure options such as client-to-client or disabled TLS auth. Secrets are masked, findings are mapped to CWE and MITRE ATT&CK, and reports export to TXT, Markdown, JSON, CSV or SARIF.

---

## ✨ Features


- OpenVPN (.conf/.ovpn) and WireGuard (wg .conf) parsers with directive and inline-key awareness
- Cipher/auth strength checks (weak/BF-CBC ciphers, missing tls-crypt/tls-auth, HMAC digest)
- Certificate and key review: CA/cert/key presence, DH params, and masked embedded secrets
- Insecure-option detection (client-to-client, duplicate-cn, no tls-version-min, 0.0.0.0 binds)
- Key/secret file-permission and ownership checks across the config tree
- CWE+ATT&CK mapping, offline --root trees and TXT/MD/JSON/CSV/SARIF export with CI gating

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OVpnAudit --scan -f sarif -o vpn.sarif
./OVpnAudit --config /etc/openvpn/server.conf
./OVpnAudit -r /mnt/image --fail-on high --json
./OVpnAudit --demo
./OVpnAudit --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
