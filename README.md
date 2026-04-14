# Linux Hardening Framework (Ansible)

A modular, extensible Ansible-based framework for hardening Linux systems using industry benchmarks and best practices.

This project began as a CIS RHEL 9 implementation and has evolved into a flexible structure that supports multiple benchmarks and distributions.

---

## Current Status

WARNING: This project is currently a work-in-progress and has not been thoroughly reviewed. It is NOT RECOMMENDED FOR USE IN PRODUCTION ENVIRONMENTS at this time. The playbooks are subject to change, and further testing and validation are required.

---

## Features

* CIS Benchmark implementation (RHEL 9)
* Modular role-based architecture
* Easily extendable for new benchmarks (STIG, NIST, etc.)
* Support for custom "general hardening" baselines
* Organized by benchmark → distribution → roles

---

## Project Structure

```
.
├── benchmarks/
│   ├── cis/
│   │   └── rhel9/
│   │       ├── cis_1_initial_setup/
│   │       ├── cis_2_services/
│   │       ├── cis_3_network/
│   │       ├── cis_4_firewall/
│   │       ├── cis_5_accessctrl/
│   │       ├── cis_6_logging_auditing/
│   │       └── cis_7_system_maintenance/
│   └── general/
│       └── fedora/
├── inventories/
├── group_vars/
├── playbooks/
├── ansible.cfg
├── requirements.yml
└── README.md
```

---

## Getting Started

### 1. Clone the Repository

```
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

---

### 2. Install Requirements

```
ansible-galaxy install -r requirements.yml
```

---

### 3. Configure Inventory

Edit or create an inventory file:

```
inventories/hosts.ini
```

Example:

```
[servers]
your-server-ip ansible_user=your-user
```

---

### 4. Run a Playbook

Apply CIS Hardening (RHEL 9):

```
ansible-playbook -i inventories/hosts.ini playbooks/cis_rhel9.yml
```

Apply General Linux Hardening:

```
ansible-playbook -i inventories/hosts.ini playbooks/general_linux.yml
```

---

## Benchmarks

### CIS (Center for Internet Security)

RHEL 9 benchmark implemented as modular roles:

* Initial setup
* Services
* Network configuration
* Firewall
* Access control
* Logging and auditing
* System maintenance

---

## Customization

You can override variables using:

* group_vars/
* host_vars/
* role defaults and vars

---

## Tags (Recommended Usage)

Run specific sections using tags:

```
ansible-playbook ... --tags ssh
ansible-playbook ... --tags firewall
```

(Tags should be defined inside roles for granular control.)

---

## Extending the Framework

To add a new benchmark or distribution:

```
benchmarks/
  └── <benchmark>/
      └── <distro>/
          ├── roles/
          └── playbook.yml
```

Examples:

* cis/ubuntu22
* stig/rhel9
* general/debian

---

## Disclaimer

This project applies security hardening that may impact system functionality.

* Test in a staging environment first
* Review changes before applying to production systems
* Some controls may require environment-specific tuning

---

## Roadmap

* Add Ubuntu CIS benchmark
* Add STIG support
* Improve tagging coverage
* Convert to Ansible Collection
* CI/CD validation (linting and test runs)

---

## Contributing

Contributions are welcome:

* Add new benchmarks
* Improve existing roles
* Fix bugs or edge cases

---

## License

MIT License (or choose your preferred license)

---

## Author

https://github.com/tmpmount
