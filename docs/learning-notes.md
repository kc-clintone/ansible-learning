# Learning Journal - Week 1 Progress

## Day 1: Ansible Basics

### What I Learned

- Ansible is agentless—huge advantage over Puppet/Chef
- Uses SSH to communicate with remote hosts
- YAML syntax for playbooks (simpler than JSON/XML)
- Control node vs. managed nodes concept

### Key Takeaway

The agentless model is clever because it reduces overhead. Every managed node doesn't need a daemon running.

### Installed Ansible

```bash
apt install ansible
ansible --version
```

Got 2.10.8 installed. Good enough for learning.

---

## Day 2: Inventory Files

### Understanding Inventory

Inventory defines which hosts Ansible manages. Simple INI format:

```ini
[webservers]
web1.local
web2.local

[databases]
db1.local
db2.local
```

### Pattern Matching

Can target specific groups:

- `ansible webservers -m ping` → ping all webservers
- `ansible all -m ping` → ping everything
- `ansible db1.local -m ping` → ping single host

### Variables in Inventory

Can set per-host variables:

```ini
[webservers]
web1.local ansible_user=ubuntu ansible_port=2222
web2.local ansible_user=ubuntu
```

---
