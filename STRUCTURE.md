# ansible-learning Repository Structure

```
.
├── README.md                           # Main repository overview
├── STRUCTURE.md                        # This file - directory guide
├── ansible.cfg                         # Ansible configuration
│
├── docs/                               # Learning documentation
│   ├── ansible-overview.md            # Core concepts and principles
│   ├── architecture.md                # Technical architecture details
│   ├── learning-notes.md              # Weekly learning journal
│   └── quick-reference.md             # Commands and modules reference
│
├── inventories/
│   └── inventory.ini                  # Host inventory with groups
│
├── playbooks/                          # Automation scripts
│   ├── ping.yml                       # Week 1: Connectivity test
│   ├── install_nginx.yml              # Week 1: Simple Nginx setup
│   ├── create_user.yml                # Week 1: User management
│   ├── module-examples.yml            # Week 2: Module reference guide
│   ├── nginx-deployment.yml           # Week 2: Advanced deployment
│   └── variables-and-facts.yml        # Week 2: Variables & facts
│
└── report/                             # Progress and learning reports
    └── learning-report.md             # Comprehensive learning report
```

## Directory Guide

### /docs - Learning Material

- **ansible-overview.md** - High-level concepts (What is Ansible?, key terms)
- **architecture.md** - Technical deep-dive (Control nodes, communication flow)
- **learning-notes.md** - Personal learning journal (Day-by-day progress)
- **quick-reference.md** - Practical guide (Commands, modules, troubleshooting)

### /inventories - Host Configuration

- **inventory.ini** - Defines hosts and groups for Ansible to manage

### /playbooks - Automation Scripts

**Week 1 Playbooks (Foundational):**

- **ping.yml** - Simple connectivity test using ping module
- **install_nginx.yml** - Installs and configures Nginx web server
- **create_user.yml** - Creates system user accounts

**Week 2 Playbooks (Intermediate):**

- **module-examples.yml** - Comprehensive reference for 10+ modules
- **nginx-deployment.yml** - Advanced deployment with variables, handlers, validation
- **variables-and-facts.yml** - Variable types, filters, and fact usage

### /report - Documentation & Progress

- **learning-report.md** - Week 1 completion status, Week 2 progress, challenges, reflections

## File Descriptions

### Core Configuration Files

| File           | Purpose                                                 |
| -------------- | ------------------------------------------------------- |
| `README.md`    | Project overview and quick start guide                  |
| `ansible.cfg`  | Ansible settings (inventory path, SSH options, logging) |
| `STRUCTURE.md` | This file - directory organization guide                |

### Documentation (docs/)

| File                  | Content                                 | Status    |
| --------------------- | --------------------------------------- | --------- |
| `ansible-overview.md` | Ansible concepts, architecture, modules | Week 1 ✅ |
| `architecture.md`     | Technical deep-dive with diagrams       | Week 1 ✅ |
| `learning-notes.md`   | Daily learning journal                  | Week 1 ✅ |
| `quick-reference.md`  | Command reference and tips              | Week 2 🔄 |

### Playbooks (playbooks/)

| File                      | Complexity        | Topics Covered                | Status    |
| ------------------------- | ----------------- | ----------------------------- | --------- |
| `ping.yml`                | ⭐ Beginner       | Basic structure, gather_facts | Week 1 ✅ |
| `install_nginx.yml`       | ⭐ Beginner       | apt, service modules          | Week 1 ✅ |
| `create_user.yml`         | ⭐ Beginner       | user, file modules            | Week 1 ✅ |
| `module-examples.yml`     | ⭐⭐ Intermediate | 8 modules, patterns           | Week 2 🔄 |
| `nginx-deployment.yml`    | ⭐⭐ Intermediate | Variables, handlers, facts    | Week 2 🔄 |
| `variables-and-facts.yml` | ⭐⭐ Intermediate | Variables, filters, loops     | Week 2 🔄 |

## Learning Progression

### Week 1: Foundation (✅ Complete)

1. Architecture understanding → architecture.md
2. Installation setup → quick-reference.md
3. Inventory creation → inventory.ini
4. Simple playbooks → ping.yml, install_nginx.yml, create_user.yml

### Week 2: Intermediate (🔄 In Progress)

1. Module deep-dive → module-examples.yml
2. Variables & facts → variables-and-facts.yml
3. Advanced deployment → nginx-deployment.yml
4. Planned: Roles, Error Handling

## How to Navigate

**For Learning:**

1. Start: `docs/ansible-overview.md`
2. Then: `docs/architecture.md`
3. Practice: `playbooks/ping.yml`
4. Progress: `playbooks/install_nginx.yml`
5. Reference: `docs/quick-reference.md`

**For Reference:**

- Commands → `docs/quick-reference.md`
- Modules → `playbooks/module-examples.yml`
- Concepts → `docs/architecture.md`
- Progress → `report/learning-report.md`

## Key Statistics

| Metric              | Count |
| ------------------- | ----- |
| Documentation files | 4     |
| Playbook examples   | 6     |
| Modules covered     | 12+   |
| Core concepts       | 12+   |
| Week 1 completion   | 100%  |
| Week 2 progress     | ~70%  |

## Status Legend

- ✅ Complete
- 🔄 In Progress
- 📋 Planned

---

Last updated: May 30, 2026
