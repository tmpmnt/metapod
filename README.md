# Metapod

A modular, extensible Ansible-based framework for hardening Linux systems using industry benchmarks and best practices.

This project began as a CIS RHEL 9 implementation and has evolved into a flexible structure that supports multiple benchmarks and distributions.

---

## Current Status

**WARNING:** This project is currently a work-in-progress and has not been thoroughly reviewed. It is **NOT RECOMMENDED FOR USE IN PRODUCTION ENVIRONMENTS** at this time. The playbooks are subject to change, and further testing and validation are required.

---

## Features

* CIS Benchmark implementation (RHEL 9)
* Modular role-based architecture
* Easily extendable for new benchmarks (STIG, NIST, etc.)
* Support for custom "general hardening" baselines
* Organized by benchmark → distribution → roles

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



---

## Author

https://github.com/tmpmount
