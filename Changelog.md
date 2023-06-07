# Changes to POSTGRES-12-CIS

## 1.0.2

- Updated License File date
- Added .yamlint file
- Updated .gitattributes file
- Updated .ansible-lint file
- Updated ReadMe file
- Updated Module names in cis_pgs12_ubuntu_fixes.yml and cis_pgs12_redhat_fixes.yml
- Added WarnCount to cis_pgs12_ubuntu_fixes.yml
- Added WarnCount to cis_pgs12_redhat_fixes.yml
- yamllint and ansiblelint updates
- Updated Module names in handlers/main.yml
- Restructured directories to CIS Repo Standard with each section and task in their own directory
- Combined separate Ubuntu vs RHEL tasks into each variablized tasks from section_1 to section_8.
- Added 'key-order' to skip in .ansible-lint file
- Added Ansible Core minimum version requirements, Distribution#, and OS_family restriction via Assert Module
- Added warn-count system for manual tasks.
- Removed all RHEL7 tagging and conditions.
- Fixed Truthy syntax, typos, and Linting.
- Removed Section* tags in each task.
- Added Vagrantfile and GitHub Workflow automation
- Updated CIS PostgreSQL 12 Benchmark baseline to v1.1.0 - 04-28-2023
