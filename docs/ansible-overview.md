# Ansible Overview - Learning Notes

## What is Ansible?

Ansible is an agentless infrastructure automation tool. Unlike other tools (Puppet, Chef), it doesn't require agents on managed nodes—it uses SSH and Python.

## Key Concepts

### Control Node

- The machine where Ansible is installed
- Runs playbooks and sends commands to managed nodes
- Can be any Linux/Mac machine, even a laptop

### Managed Nodes

- The target machines that Ansible configures
- Need Python installed (most systems have it)
- SSH access required from control node

### Inventory

- Defines which hosts Ansible will manage
- Can be static (INI/YAML files) or dynamic (cloud APIs)
- Groups hosts for easier management

### Playbooks

- YAML files describing automation tasks
- Contain plays and tasks
- Idempotent—safe to run multiple times

## Ansible Architecture Flow

```
Control Node
├── Reads inventory.ini
├── Loads playbook.yml
├── Generates Python code
└── Sends to Managed Nodes via SSH
         │
         ├─→ Host1 (executes Python module)
         ├─→ Host2 (executes Python module)
         └─→ Host3 (executes Python module)
```

## Why Ansible?

1. **Agentless** - No software to install on servers
2. **Simple** - YAML syntax, easy to learn
3. **Powerful** - Can do complex multi-tier deployments
4. **Idempotent** - Tasks are safe to repeat

## Common Modules Learned

- `ping` - Test connectivity
- `apt` - Package management (Debian/Ubuntu)
- `service` - Start/stop/restart services
- `copy` - Copy files to remote hosts
- `user` - Manage user accounts
- `command` - Run raw commands

## Installation Notes

Installed via `apt` on Ubuntu. Uses Python for communication with remote hosts.
