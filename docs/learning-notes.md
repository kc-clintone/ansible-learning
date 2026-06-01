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

## Day 3: First Playbook

### Running ping.yml

Created a simple playbook:

```yaml
---
- hosts: all
  tasks:
    - name: Ping all hosts
      ping:
```

Key learning: Even simple playbook shows structure—hosts, tasks, module name.

### Understanding Module Output

Modules return JSON with:

- `changed`: Did task make a change?
- `unreachable`: Host not accessible
- `failed`: Task failed
- Module-specific data

Idempotence important: if system already in desired state, `changed: false`.

---

## Day 4: Basic Modules

### apt Module

```yaml
- name: Install nginx
  apt:
    name: nginx
    state: present
    update_cache: yes
```

Learning point: `state: present` means "ensure it's installed". If already installed, no action taken.

### service Module

```yaml
- name: Start nginx
  service:
    name: nginx
    state: started
    enabled: yes
```

`enabled: yes` makes service start on boot.

### copy Module

```yaml
- name: Copy config file
  copy:
    src: /local/path/nginx.conf
    dest: /etc/nginx/nginx.conf
    owner: root
    group: root
    mode: "0644"
```

Mode in octal format. Need quotes around it.

---

## Day 5: User Management

### user Module

```yaml
- name: Create application user
  user:
    name: appuser
    state: present
    shell: /bin/bash
    createhome: yes
    groups: sudo
```

`groups: sudo` adds to sudo group. Cool for permission management.

---

## Week 1 Reflection

### What Went Well

✓ Understood basic architecture quickly
✓ Got hands-on with modules
✓ Recognized the power of idempotence
✓ Inventory system makes sense

### Challenges

✗ SSH key setup was confusing at first
✗ Debugging module errors (had to read docs)
✗ Understanding `changed` vs `failed` initially

### Week 2 Plans

- Deep dive into variables and facts
- Build more complex playbooks
- Explore roles for code reuse
- Nginx installation playbook as practical project
