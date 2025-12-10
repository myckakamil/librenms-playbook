LibreNMS Playbook
===
Playbook ansible for automated [LibreNMS](https://www.librenms.org/) installation and setup. 

Quick start
---
- clone repository
- Install required Ansible role:
```
ansible-galaxy install myckakamil.snmpd
```
- Customize your inventory file
- Set your variables
- Run playbook
```
ansible-playbook -i inventory.ini playbook.yaml
```

Requirements
---
- Debian 11 or newer
- Python3 installed
- [myckakamil.snmpd](https://galaxy.ansible.com/ui/standalone/roles/myckakamil/snmpd/) role installed
- Root or sudo access

Inventory setup
---
Create `inventory.ini` file with your server details:
```ini
[librenms_server]
librenms.example.com

[librenms_server:vars]
ansible_user=user
ansible_python_interpreter=/usr/bin/python3.13
```

Configuration
---
Non-sensitive configuration is stored in `vars/config.yaml`
```
---
librenms_varsion: "25.10.0"
tz: "Europe/Warsaw"
librenms_domain: librenms.example.com
```
All sensitive variables are stored in `vars/vault.yaml`
```
---
librenms_password: P@$$w0rd
snmp_community: public
snmp_email: email@example.com
snmp_location: City
```

Todo
---
- [ ] - make this playbook compatible with RHEL systems
- [ ] - split tasks into seperate roles
