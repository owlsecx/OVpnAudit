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

Offline OpenVPN / WireGuard / IPsec configuration auditor

---

## ✨ Features

- OpenVPN server/client parser (.conf / .ovpn) with inline-block (<ca>/<key>/<tls-crypt>) awareness
- OpenVPN checks — cipher / data-ciphers / auth digest, tls-version-min, tls-auth / tls-crypt, VORACLE compression, client-to-client, duplicate-cn, script-security 3, privilege drop, verify-x509-name, remote-cert-tls, static keys, management socket ...
- WireGuard parser — AllowedIPs on servers, missing PresharedKey, key file permissions, PostUp/PostDown shell hooks, duplicate / self public keys, overlaps
- Pure-python X25519 — derives WireGuard public keys from private keys to catch key reuse across files
- strongSwan ipsec.conf / swanctl.conf + libreswan — IKEv1 aggressive mode, 3DES / MD5 / modp1024 proposals, PFS, PSK strength, ipsec.secrets perms
- Rule catalogue with CWE + MITRE ATT&CK mapping, severity and remediation for every finding
- Secret masking — inline keys / PSKs never printed
- Filesystem sweep (--root) of /etc/openvpn, /etc/wireguard, /etc/ipsec*, /etc/swanctl, ...
- Weighted 0–100 score and A+…F grade per file
- Export TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Built-in --demo self-test (weak vs. hardened set)
- Full CLI mode with --min-severity / --fail-on gates

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OVpnAudit
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
