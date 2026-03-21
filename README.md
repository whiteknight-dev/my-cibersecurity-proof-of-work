# 🛡️ My Cibersecurity Proof-of-work

> Everything I've learned, practiced and broken stay here.

---

## 👤 About this repo

This repo is my public logbook: every file is a lesson I have learned in my own words.

**Objetivo**: I'm sharing my learning journey through my perspective, putting into practice everything I have learned in a practical way.

---

## 📁 Structure

```
cybersecurity-notes/
│
├── 📂 networking/          # Networking, protocols, subnets
├── 📂 linux/               # File system, permission, commands, bash
├── 📂 windows/             # AD, PowerShell, NTFS, registry
└── 📄 README.md            # Index
```

---

## 🗂️ Index

### 🌐 Networking

| Lección                                                                 | Descripción                          | Lab |
| ----------------------------------------------------------------------- | ------------------------------------ | --- |
| [Introduction to Networks](./Networking/01-introduction-to-networks.md) | Basic concepts about Networks        | --  |
| [OSI TPC-IP Models](./Networking/02-osi-tcp-models.md)                  | Layes and what is their function     | --  |
| [MAC IP Ports](./Networking/03-mac-ip-ports.md)                         | How the traffic moves in networks    | --  |
| [TCP vs UDP](./)                                                        | Diferencias, casos de uso y capturas | --  |
| [Subnetting](./)                                                        | CIDR, máscaras, cálculo de rangos    | --  |

### 🐧 Linux

| Lección                   | Descripción                               | Lab |
| ------------------------- | ----------------------------------------- | --- |
| [Sistema de archivos](./) | Jerarquía FHS, rutas importantes          | --  |
| [Permisos](./)            | rwx, chmod, chown, SUID/SGID              | --  |
| [Bash básico](./)         | Comandos esenciales, redirecciones, pipes | --  |

### 🪟 Windows

| Lección                | Descripción                      | Lab |
| ---------------------- | -------------------------------- | --- |
| [Active Directory](./) | Usuarios, grupos, GPOs           | --  |
| [PowerShell](./)       | Comandos, scripts, ejecución     | --  |
| [Registro](./)         | Hives, rutas clave, persistencia | --  |

---

## 🖥️ Hack The Box

Máquinas resueltas ordenadas por dificultad:

| Machine                    | OS      | Difficulty | Vectors                         | Writeup                                             |
| -------------------------- | ------- | ---------- | ------------------------------- | --------------------------------------------------- |
| Starting Point - Responder | Windows | Very Easy  | LFI, RFI, NTLM Capture Attack   | [Responder](./Machines/responder-starting-point.md) |
| Starting Point - Three     | Linux   | Very Easy  | DNS Enumeration, Web Shell, RCE | [Responder](./Machines/three-starting-point.md)     |

> _Se irán agregando a medida que las resuelva._

---

## 📈 My Progress

- [x] Start CJCA
- [x] Complete Networking Module
- [ ] Completar módulo de Linux
- [ ] Completar módulo de Windows
- [x] First HTB Machine (easy)
- [ ] 15 máquinas resueltas en HTB

---

## 🔗 Resources

- [Hack The Box Academy](https://academy.hackthebox.com)
- [TryHackMe](https://tryhackme.com)
- [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/)

---

_Last Update: 03-20-2026_
