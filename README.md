# Ansible Learning Journey

_A structured, hands-on exploration of infrastructure automation with Ansible_

---

## 📋 Project Overview

This repository documents my systematic learning journey through **Ansible**, an agentless infrastructure automation and configuration management platform. The project progresses from foundational concepts to practical deployments, with emphasis on understanding core principles and building reusable automation code.

**Timeline:** Week 1 ✅ Complete | Week 2 🔄 In Progress  
**Current Focus:** Modules, Variables, and Advanced Playbooks

---

## 📚 Topics Covered

| Week | Topic                  | Status         | Files                                                        |
| ---- | ---------------------- | -------------- | ------------------------------------------------------------ |
| 1    | Ansible Architecture   | ✅ Complete    | [architecture.md](docs/architecture.md)                      |
| 1    | Inventory Management   | ✅ Complete    | [inventory.ini](inventories/inventory.ini)                   |
| 1    | First Playbooks        | ✅ Complete    | [playbooks/](playbooks/)                                     |
| 2    | Core Modules Deep-Dive | 🔄 In Progress | [module-examples.yml](playbooks/module-examples.yml)         |
| 2    | Variables & Facts      | 🔄 In Progress | [variables-and-facts.yml](playbooks/variables-and-facts.yml) |
| 2    | Advanced Deployment    | 🔄 In Progress | [nginx-deployment.yml](playbooks/nginx-deployment.yml)       |

---

## 📁 Repository Structure

```
ansible-learning/
├── docs/                          # Learning documentation
│   ├── ansible-overview.md       # Core concepts & architecture
│   ├── architecture.md           # Technical deep-dive
│   ├── learning-notes.md         # Week-by-week journal
│   └── quick-reference.md        # Commands & modules guide
│
├── inventories/
│   └── inventory.ini             # Host definitions & groups
│
├── playbooks/                     # Automation scripts
│   ├── ping.yml                  # Basic connectivity test
│   ├── install_nginx.yml         # Simple Nginx installation
│   ├── create_user.yml           # User account management
│   ├── module-examples.yml       # Module reference guide
│   ├── nginx-deployment.yml      # Advanced deployment
│   └── variables-and-facts.yml   # Variable & fact examples
│
├── report/
│   └── learning-report.md        # Comprehensive progress report
│
├── ansible.cfg                   # Ansible configuration
└── README.md                     # This file
```

---

## 🎯 Learning Outcomes Achieved

### Week 1: Foundations ✅

- ✅ **Architecture Understanding** - Control nodes, managed nodes, agentless design
- ✅ **Environment Setup** - Ansible installation and SSH configuration
- ✅ **Inventory Management** - Host grouping and variable assignment
- ✅ **Basic Playbooks** - Structure, tasks, and idempotence
- ✅ **Essential Modules** - apt, service, copy, user, command

### Week 2: Intermediate ✅ (In Progress)

- 🔄 **Module Mastery** - Deep-dive into 10+ Ansible modules
- 🔄 **Variables & Facts** - Variable types, filters, and facts gathering
- 🔄 **Advanced Playbooks** - Handlers, pre/post-tasks, validation
- 📋 **Roles** - Planned for structured reusability
- 📋 **Error Handling** - Planned for production reliability

---

## 🚀 Quick Start

### View Learning Materials

```bash
cat docs/ansible-overview.md      # Concepts
cat docs/architecture.md          # Technical details
cat docs/quick-reference.md       # Commands guide
```

### Test Connectivity

```bash
ansible all -m ping
```

### Run Example Playbooks

```bash
# Simple connectivity test
ansible-playbook playbooks/ping.yml

# Install and configure Nginx
ansible-playbook playbooks/install_nginx.yml

# Create system user
ansible-playbook playbooks/create_user.yml

# Learn about modules
ansible-playbook playbooks/module-examples.yml --check

# Advanced deployment
ansible-playbook playbooks/nginx-deployment.yml

# Variables and facts
ansible-playbook playbooks/variables-and-facts.yml
```

---

## 📝 Playbook Details

| Playbook                    | Purpose                 | Demonstrates                           | Difficulty   |
| --------------------------- | ----------------------- | -------------------------------------- | ------------ |
| **ping.yml**                | Test host connectivity  | Basic structure, gather_facts          | Beginner     |
| **install_nginx.yml**       | Install web server      | apt, service modules, verification     | Beginner     |
| **create_user.yml**         | User account management | user module, file permissions          | Beginner     |
| **module-examples.yml**     | Module reference guide  | 10+ modules, common patterns           | Intermediate |
| **nginx-deployment.yml**    | Production-like setup   | Variables, handlers, facts, validation | Intermediate |
| **variables-and-facts.yml** | Variable types & usage  | Facts, filters, loops, conditionals    | Intermediate |

---

## 🔧 Modules Covered

**Package Management:**

- `apt` - Debian/Ubuntu package management

**Service Management:**

- `service` - Start/stop/restart services
- `service_facts` - Query service status

**File Operations:**

- `copy` - Copy files to remote hosts
- `file` - Create/modify directories and symlinks

**User Management:**

- `user` - Create and manage user accounts
- `getent` - Query system databases

**Command Execution:**

- `command` - Execute raw commands
- `shell` - Execute commands with pipes

**Monitoring & Testing:**

- `ping` - Test connectivity
- `uri` - Test HTTP connectivity

**Utility:**

- `debug` - Display variables and output
- `set_fact` - Create custom facts

---

## 📖 Documentation Highlights

### Conceptual Learning

- [ansible-overview.md](docs/ansible-overview.md) - High-level concepts
- [architecture.md](docs/architecture.md) - Technical architecture with diagrams
- [learning-notes.md](docs/learning-notes.md) - Week-by-week learning journal

### Practical Reference

- [quick-reference.md](docs/quick-reference.md) - Command reference and tips
- [module-examples.yml](playbooks/module-examples.yml) - Working module examples
- [variables-and-facts.yml](playbooks/variables-and-facts.yml) - Variable usage examples

### Progress Tracking

- [learning-report.md](report/learning-report.md) - Comprehensive progress report

---

## 🎓 Key Concepts Mastered

1. **Idempotence** - Tasks reach desired state safely, repeated execution is safe
2. **Agentless Architecture** - SSH-based, no persistent daemons required
3. **YAML Syntax** - Clean, readable automation code
4. **Module-based Design** - Consistent interface for infrastructure operations
5. **Handlers** - Efficient notification system for conditional actions
6. **Facts** - System information for dynamic playbook behavior
7. **Variables** - Configuration management and code reusability

---

## 🛠 Technologies & Environment

- **OS:** Ubuntu 26.04 LTS
- **Ansible Version:** 2.10+
- **Control Node:** Development machine (local)
- **Managed Nodes:** localhost + VMs
- **Configuration:** ansible.cfg for project-specific settings

---

## 📊 Progress Summary

| Category        | Week 1  | Week 2 | Total        |
| --------------- | ------- | ------ | ------------ |
| Documentation   | 3 files | 1 file | 4 files      |
| Playbooks       | 3       | 3      | 6 playbooks  |
| Modules Covered | 6       | 10+    | 12+ modules  |
| Concepts        | 7       | 5+     | 12+ concepts |

---

## 🔍 How to Use This Repository

1. **Learn Concepts First** - Start with docs/ folder
   - Read `ansible-overview.md` for concepts
   - Read `architecture.md` for technical details

2. **Examine Playbooks** - Study real working examples
   - Start with simple playbooks (ping, install_nginx)
   - Progress to advanced examples (nginx-deployment)

3. **Run Playbooks** - Get hands-on experience
   - Test with `--check` flag first
   - Run against localhost for safety

4. **Review Progress** - Check learning-report.md for detailed progress

---

## 💡 Key Takeaways

- **Ansible Makes Automation Accessible** - YAML + modules = infrastructure code
- **Agentless is Powerful** - SSH-based approach reduces complexity
- **Idempotence Enables Confidence** - Safe to run repeatedly
- **Progressive Learning Works** - Simple → Advanced playbooks

---

## 📈 Next Steps

- [x] Implement Ansible Roles for modularity
- [ ] Build comprehensive error handling (block/rescue/always)
- [ ] Create multi-tier deployment examples
- [ In progress ] Integrate with CI/CD pipelines
- [ ] Explore dynamic inventory
- [ ] Production hardening practices

---

## 📞 Learning Resources Used

- Official Ansible Documentation
- Red Hat Ansible
- Hands-on experimentation
- Playbook examples
- Module documentation reference

---

**Last Updated:** July 24, 2026  
**Status:** Active Learning - Week 4 In Progress  
**License:** Learning Project

---

_This repository represents genuine learning progress through structured, hands-on exploration of Ansible infrastructure automation._
