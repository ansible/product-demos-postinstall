# Product Demos postinstall repo

This repository contains configuration used to add the [Ansible Product Demos](https://github.com/ansible/product-demos) to a new Ansible Automation Platform deployment during the post-installation process.  It takes advantage of the containerized AAP feature for [pre-seeding configuration and content at installation time](https://www.redhat.com/en/blog/seeding-ansible-automation-platform-content-at-installation-time).

## Using this repo

In the installation inventory file you will use to install a containerized Ansible Automation Platform environment, add the following variables under the `[all:vars]` section in addition to any other required variables:

```
[all:vars]
controller_postinstall=true
controller_postinstall_repo_url=https://github.com/ansible/product-demos-postinstall.git
controller_postinstall_dir=./product-demos-postinstall
```

When you [install containerized Ansible Automation Platform](https://docs.redhat.com/en/documentation/red_hat_ansible_automation_platform/2.4/html/containerized_ansible_automation_platform_installation_guide/aap-containerized-installation#installing-containerized-aap_aap-containerized-installation), this repository will be cloned and used to configure the automation controller with the Ansible Product Demos configuration components.
