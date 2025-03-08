
Отличная идея! Использование Ansible в связке с GitHub CI/CD позволит автоматизировать настройку сервера. Вот как это можно организовать:

---

### 1. Структура репозитория
```
your-repo/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── ansible/
│   ├── inventory.ini
│   ├── playbook.yml
│   └── roles/
│       └── server-setup/
│           ├── handlers/
│           │   └── main.yml
│           ├── tasks/
│           │   └── main.yml
│           └── vars/
│               └── main.yml
└── README.md
```

# Auto-Setup Server

## Requirements
- Ubuntu 22.04+ server
- GitHub Secrets:
  - `SERVER_IP`
  - `ROOT_PASSWORD`
  - `HASH_PASSWORD`

## Usage
1. Clone repo
2. Configure secrets in GitHub
3. Push to `main` branch

## Post-Install
Connect using:
```bash
ssh root@SERVER_IP  # Password: ROOT_PASSWORD
ssh hash@SERVER_IP  # Password: HASH_PASSWORD
```
