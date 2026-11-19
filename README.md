rhel10-ldap-authentication/
│
├── README.md
├── LICENSE
├── .gitignore
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
├── screenshots/
│   ├── 01-server-status.png
│   ├── 02-ldap-port.png
│   ├── 03-directory-tree.png
│   ├── 04-ldap-user.png
│   ├── 05-ldap-group.png
│   ├── 06-client-sssd.png
│   └── 07-rahul-login.png
│
└── tests/
    ├── test-ldap-connection.sh
    ├── test-user-search.sh
    └── test-client-login.sh
