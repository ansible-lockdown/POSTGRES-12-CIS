# PostgresSQL 12 CIS

## Configure a PostgresSQL 12 machine to be [CIS](https://www.cisecurity.org/cis-benchmarks/) compliant

### Based on [CIS PostgreSQL 12 Benchmark v1.0.0 - 11-19-2019](https://www.cisecurity.org/cis-benchmarks/)

---

![Org Stars](https://img.shields.io/github/stars/ansible-lockdown?label=Org%20Stars&style=social)
![Stars](https://img.shields.io/github/stars/ansible-lockdown/POSTGRES-12-CIS?label=Repo%20Stars&style=social)
![Forks](https://img.shields.io/github/forks/ansible-lockdown/POSTGRES-12-CIS?style=social)
![followers](https://img.shields.io/github/followers/ansible-lockdown?style=social)
[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/AnsibleLockdown.svg?style=social&label=Follow%20%40AnsibleLockdown)](https://twitter.com/AnsibleLockdown)

![Discord Badge](https://img.shields.io/discord/925818806838919229?logo=discord)

![Devel Build Status](https://img.shields.io/github/actions/workflow/status/ansible-lockdown/POSTGRES-12-CIS/linux_benchmark_testing.yml?label=Devel%20Build%20Status)
![Devel Commits](https://img.shields.io/github/commit-activity/m/ansible-lockdown/POSTGRES-12-CIS/devel?color=dark%20green&label=Devel%20Branch%20commits)

![Release Branch](https://img.shields.io/badge/Release%20Branch-Main-brightgreen)
![Main Build Status](https://img.shields.io/github/actions/workflow/status/ansible-lockdown/POSTGRES-12-CIS/linux_benchmark_testing.yml?label=Build%20Status)
![Main Release Date](https://img.shields.io/github/release-date/ansible-lockdown/POSTGRES-12-CIS?label=Release%20Date)
![Release Tag](https://img.shields.io/github/v/tag/ansible-lockdown/POSTGRES-12-CIS?label=Release%20Tag&&color=success)

![Issues Open](https://img.shields.io/github/issues-raw/ansible-lockdown/POSTGRES-12-CIS?label=Open%20Issues)
![Issues Closed](https://img.shields.io/github/issues-closed-raw/ansible-lockdown/POSTGRES-12-CIS?label=Closed%20Issues&&color=success)
![Pull Requests](https://img.shields.io/github/issues-pr/ansible-lockdown/POSTGRES-12-CIS?label=Pull%20Requests)

![License](https://img.shields.io/github/license/ansible-lockdown/POSTGRES-12-CIS?label=License)

---

## Looking for support?

[Lockdown Enterprise](https://www.lockdownenterprise.com#GH_AL_POSTGRES_12_CIS)

[Ansible support](https://www.mindpointgroup.com/cybersecurity-products/ansible-counselor#GH_AL_POSTGRES_12_CIS)

### Community

Join us on our [Discord Server](https://discord.io/ansible-lockdown) to ask questions, discuss features, or just chat with other Ansible-Lockdown users.

---

## Caution(s)

This role **will make changes to the system** which may have unintended consequences. This is not an auditing tool but rather a remediation tool to be used after an audit has been conducted.

Check Mode is not supported! The role will complete in check mode without errors, but it is not supported and should be used with caution. The POSTGRES-12-CIS role or a compliance scanner should be used for compliance checking over check mode.

This role was developed against a clean install of the Application. If you are implementing to an existing system please review this role for any site specific changes that are needed.

To use release version please point to main branch and relevant release for the cis benchmark you wish to work with.

---

## Matching a security Level for CIS

The control found in defaults main also need to reflect this as this control the testing that takes place if you are using the audit component.

## Coming from a previous release

CIS release always contains changes, it is highly recommended to review the new references and available variables. This have changed significantly since Ansible-Lockdown initial release.

This is now compatible with python3 if it is found to be the default interpreter. This does come with pre-requisites which it configures the system accordingly.

Further details can be seen in the [Changelog](./ChangeLog.md)

## Documentation

- [Read The Docs](https://ansible-lockdown.readthedocs.io/en/latest/)
- [Getting Started](https://www.lockdownenterprise.com/docs/getting-started-with-lockdown#GH_AL_POSTGRES_12_CIS)
- [Customizing Roles](https://www.lockdownenterprise.com/docs/customizing-lockdown-enterprise#GH_AL_POSTGRES_12_CIS)
- [Per-Host Configuration](https://www.lockdownenterprise.com/docs/per-host-lockdown-enterprise-configuration#GH_AL_POSTGRES_12_CIS)
- [Getting the Most Out of the Role](https://www.lockdownenterprise.com/docs/get-the-most-out-of-lockdown-enterprise#GH_AL_POSTGRES_12_CIS)

## Requirements

- Postgres12x
- ansible 2.10
- jmespath
- relevant collections

**General:**

- Basic knowledge of Ansible, below are some links to the Ansible documentation to help get started if you are unfamiliar with Ansible

  - [Main Ansible documentation page](https://docs.ansible.com)
  - [Ansible Getting Started](https://docs.ansible.com/ansible/latest/user_guide/intro_getting_started.html)
  - [Tower User Guide](https://docs.ansible.com/ansible-tower/latest/html/userguide/index.html)
  - [Ansible Community Info](https://docs.ansible.com/ansible/latest/community/index.html)
- Functioning Ansible and/or Tower Installed, configured, and running. This includes all of the base Ansible/Tower configurations, needed packages installed, and infrastructure setup.
- Please read through the tasks in this role to gain an understanding of what each control is doing. Some of the tasks are disruptive and can have unintended consequences in a live production system. Also familiarize yourself with the variables in the defaults/main.yml file.

**Technical Dependencies:**

- Python3
- Ansible 2.10+
- python-def (should be included in RHEL 9)
- libselinux-python
- pip packages
  - jmespath ( complete list found in [requirements](./requirements.txt) )
- collections found in collections/requirements.yml

## Role Variables

This role is designed that the end user should not have to edit the tasks themselves. All customizing should be done by overriding the required variables as found in defaults/main.yml file. e.g. using inventory, group_vars, extra_vars

## Tags

There are many tags available for added control precision. Each control has it's own set of tags noting what level, if it's a patch or audit, and the rule number.

Below is an example of the tag section from a control within this role. Using this example if you set your run to skip all controls with the tag services, this task will be skipped. The opposite can also happen where you run only controls tagged with services.

```sh
      tags:
      - level1-postgresql
      - audit
      - rule_1.1
```

## Community Contribution

We encourage you (the community) to contribute to this role. Please read the rules below.

- Your work is done in your own individual branch. Make sure to Signed-off and GPG sign all commits you intend to merge.
- All community Pull Requests are pulled into the devel branch.
- Pull Requests into devel will confirm your commits have a GPG signature, Signed-off, and a functional test before being approved.
- Once your changes are merged and a more detailed review is complete, an authorized member will merge your changes into the main branch for a new release.
