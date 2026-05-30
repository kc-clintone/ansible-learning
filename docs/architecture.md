# Ansible Architecture Deep Dive

## System Architecture

### Three Main Components

#### 1. Control Node (Ansible Host)

```
┌─────────────────────────────┐
│     Control Node            │
├─────────────────────────────┤
│ • Ansible Installation      │
│ • Playbooks                 │
│ • Inventory Files           │
│ • SSH Keys                  │
└──────────────┬──────────────┘
               │ SSH
               ├─────→ Managed Node 1
               ├─────→ Managed Node 2
               └─────→ Managed Node 3
```

#### 2. Managed Nodes

- Remote servers being configured
- Don't need Ansible installed
- Need SSH access and Python

#### 3. Connection Layer

- Uses SSH for communication
- Python modules execute on remote nodes
- Results sent back to control node

## Playbook Execution Flow

```
1. Parse playbook.yml
   ↓
2. Read inventory (which hosts to target)
   ↓
3. For each task:
   - Determine which module to use
   - Generate Python code for module
   - Copy to remote host via SSH
   - Execute on remote host
   - Collect results
   ↓
4. Report success/failure
```

## Key Files

### ansible.cfg

- Configuration file for Ansible
- Specifies inventory location, connection settings, etc.
- Can be local to project or system-wide

### Inventory File (inventory.ini)

```ini
[webservers]
web1.example.com
web2.example.com

[databases]
db1.example.com ansible_user=dbadmin
db2.example.com ansible_user=dbadmin
```

### Playbook Structure

```yaml
---
- hosts: webservers
  tasks:
    - name: Task description
      module_name:
        parameter: value
```

## Communication Mechanism

Ansible doesn't keep persistent connections. For each task:

1. **Connect** via SSH
2. **Gather Facts** (optional, gets system info)
3. **Execute Module** (Python code runs on remote)
4. **Disconnect** SSH
5. **Report Result** back to control node

This is why Ansible is "agentless"—no persistent daemon needed.

## Idempotence Principle

Most Ansible modules are idempotent: running the same task multiple times produces the same result.

Example:

```yaml
- name: Install nginx
  apt:
    name: nginx
    state: present
```

First run: Installs nginx
Second run: Detects nginx already installed, does nothing
Third run: Same as second run

This makes Ansible safe for repeated execution.
