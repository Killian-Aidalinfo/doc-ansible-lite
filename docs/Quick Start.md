
# Quick Start Guide

This guide will help you get started with **Ansible Lite** by showing you how to install the sources and configure your repositories for monitoring.

## Installation

To install **Ansible Lite**, follow these steps:


```bash
  curl -fsSL https://aidalinfo.github.io/aidalinfo-source/aidalinfo.gpg.key -o /etc/apt/keyrings/aidalinfo.asc
  echo "deb [trusted=yes] https://aidalinfo.github.io/aidalinfo-source/ stable main" | sudo tee /etc/apt/sources.list.d/aidalinfo.list
  sudo apt update
  sudo apt install ansible-lite
```
## Configuration

The main configuration files for Ansible Lite are located in /etc/ansible-lite. The most important file is repos.yaml, which allows you to configure the GitHub repositories to monitor.

/etc/ansible-lite/repos.yaml
Here’s an example configuration for monitoring repositories:

```yaml
repos:
  demo:
    url: "https://github.com/Killian-Aidalinfo/demo-ansible-lite"
    watcher: "*/2 * * * *"
    init: "init.sh"
    branch: "main"
    path: "/tmp/"
    auth: true
```

### Explanation of the fields:

- repos: This is the top-level key that contains all the repositories you want to monitor.

- demo: The name of the repository block (you can change this to any name you'd like).

- url: The URL of the GitHub repository to monitor.

- watcher: The cron schedule for how often to check the repository for changes (e.g., every 2 minutes).

- init: The entry script to execute when a new commit is detected (in this example, init.sh).

- branch: The branch to monitor (e.g., main).

- path: The local directory where the repository will be cloned.

- auth: Whether to use authentication (true or false).


### Editing repos.yaml
Open the configuration file for editing:

```bash
  sudo nano /etc/ansible-lite/repos.yaml
```
Add your repositories using the format above, and save the file.

Restart the ansible-lite service to apply your configuration:

```bash
sudo systemctl restart ansible-lite
```
Note: Any changes to repos.yaml require restarting the ansible-lite service to take effect.

You’re all set! Ansible Lite will now manage your repositories, execute your scripts on new commits, and help automate your server management.