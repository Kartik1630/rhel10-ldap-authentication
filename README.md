# 🚀 RHEL 10 LDAP Server and Client Authentication

**Centralized Linux User Authentication Using 389 Directory Server and SSSD**

## 📌 Project Overview

This project demonstrates centralized user authentication on Red Hat Enterprise Linux 10 using LDAP (Lightweight Directory Access Protocol).

The project uses 389 Directory Server to manage users and groups centrally and SSSD to authenticate LDAP users on another RHEL 10 client machine.

The goal is to manage Linux users from a central LDAP server and allow them to log in to multiple Linux client machines using the same credentials.

## 🛠️ Technologies Used

- Red Hat Enterprise Linux 10
- 389 Directory Server
- LDAP (Lightweight Directory Access Protocol)
- SSSD (System Security Services Daemon)
- OpenLDAP Client Tools
- LDIF Configuration
- VMware Workstation 17
- Linux Shell Scripting
- Git & GitHub

## 📂 Project Structure

```text
rhel10-ldap-authentication/
│
├── README.md
│
├── server/
│   ├── install/
│   │   └── install-389ds.sh
│   │
│   ├── config/
│   │   ├── instance-example.inf
│   │   └── firewall-setup.sh
│   │
│   ├── ldif/
│   │   ├── base-structure.ldif
│   │   ├── users/
│   │   │   └── rahul.ldif
│   │   └── groups/
│   │       └── developers.ldif
│   │
│   └── scripts/
│       ├── add-user.sh
│       ├── add-group-member.sh
│       └── verify-ldap.sh
│
├── client/
│   ├── install-client.sh
│   ├── sssd.conf.example
│   └── configure-authselect.sh
│
├── docs/
│   ├── architecture.md
│   ├── installation-guide.md
│   ├── server-configuration.md
│   ├── client-configuration.md
│   ├── user-management.md
│   ├── verification.md
│   └── troubleshooting.md
│
├── tests/
│   ├── test-ldap-connection.sh
│   ├── test-user-search.sh
│   └── test-client-login.sh
│
├── screenshots/
│
├── .gitignore
│
└── LICENSE
```

## 🎯 Project Objectives

1. Install and configure 389 Directory Server on RHEL 10.
2. Create an LDAP directory structure and configure the Base DN.
3. Create organizational units for People and Groups.
4. Create and manage LDAP users.
5. Create groups and manage group membership.
6. Configure LDAP client authentication using SSSD.
7. Enable centralized Linux user authentication.
8. Allow LDAP users to log in from another RHEL 10 machine.
9. Verify LDAP connectivity and authentication.
10. Automate administration tasks using shell scripts.

## ⚙️ Installation Requirements

- RHEL 10 LDAP Server
- RHEL 10 Client Machine
- VMware Workstation 17
- Minimum 2 GB RAM per virtual machine (4 GB recommended)
- Network connectivity between server and client
- 389 Directory Server packages
- SSSD and OpenLDAP client packages
- Root or sudo privileges

## 🗂️ LDAP Directory Structure

```text
dc=skynet,dc=com
│
├── ou=People
│   └── uid=rahul
│
└── ou=Groups
    └── cn=developers
```

### LDAP Server Information

| Configuration | Value |
|---|---|
| Server Hostname | ldap.skynet.com |
| Instance Name | ldap |
| Base DN | dc=skynet,dc=com |
| Users OU | ou=People |
| Groups OU | ou=Groups |
| LDAP Port | 389 |
| Example User | rahul |
| Example Group | developers |

## 🚀 Installation Steps

1. Install RHEL 10 on the LDAP server.
2. Configure the server hostname and network.
3. Install 389 Directory Server.
4. Create the LDAP instance using `dscreate interactive`.
5. Configure the LDAP suffix and Base DN.
6. Create People and Groups organizational units.
7. Add LDAP users using LDIF files.
8. Create groups and configure membership.
9. Set passwords for LDAP users.
10. Configure firewall access.
11. Install SSSD and LDAP client packages on the second RHEL 10 machine.
12. Configure `/etc/sssd/sssd.conf`.
13. Configure authentication using Authselect.
14. Enable and start SSSD.
15. Test LDAP user authentication from the client machine.

## 🔍 Verification Commands

### LDAP Server Verification

```bash
systemctl status dirsrv@ldap

ss -lntp | grep ':389'

ldapsearch -x -H ldap://127.0.0.1:389 \
-b "" -s base namingContexts
```

### LDAP User Verification

```bash
ldapsearch -x -H ldap://127.0.0.1:389 \
-b "dc=skynet,dc=com" "(uid=rahul)"
```

### LDAP Client Verification

```bash
systemctl status sssd

sssctl config-check

getent passwd rahul

id rahul
```

### Test LDAP User Login

```bash
su - rahul

whoami

id
```

Expected username:

```text
rahul
```

## 📸 Project Screenshots

Screenshots demonstrating the LDAP server configuration and successful client authentication will be added here.

1. LDAP Server Installation
2. Directory Server Service Status
3. LDAP Port Configuration
4. LDAP Directory Structure
5. LDAP User Creation
6. LDAP Group Management
7. SSSD Client Configuration
8. Successful Rahul Login from Another RHEL 10 Machine

## 📚 Learning Outcomes

- Linux system administration
- LDAP directory services
- 389 Directory Server configuration
- Centralized user and group management
- LDIF file management
- SSSD configuration
- Linux authentication using PAM and NSS
- Network and firewall configuration
- Shell scripting and automation
- Git and GitHub workflow
- Linux troubleshooting

## 👨‍💻 Author

**Kartik Shinde**

GitHub: [@Kartik1630](https://github.com/Kartik1630)

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for details.
