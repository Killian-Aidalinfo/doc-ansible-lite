# Ansible Lite (Beta)

**Ansible Lite** is a lightweight automation tool designed to simplify infrastructure management without the overhead of traditional Ansible. This project was born from the desire to have a management system for around ten servers, without the need to set up a centralized Ansible server, which requires physical and hardware resources.

This version is currently in **beta** and under development. If you encounter any issues or bugs, please feel free to open an issue on GitHub: [https://github.com/aidalinfo/ansible-lite/issues](https://github.com/aidalinfo/ansible-lite/issues).

## Project goals

**Ansible Lite** offers a decentralized solution, ideal for small infrastructures. Unlike other tools that require agent servers or complex setups, **Ansible Lite** relies on a simple system that monitors GitHub repositories with a cron **watcher** to detect changes and execute the appropriate actions.

## How It Works

The core functionality of **Ansible Lite** is based on monitoring GitHub repositories. Here's how it works:

- **No direct SSH instructions**: Unlike most infrastructure management tools, **Ansible Lite** focuses only on monitoring changes in GitHub repositories.

- A **watcher** is configured with a **cron** job to regularly monitor repositories.

- On each cron execution, the watcher checks if a new commit has been made since the last execution.

- If a new commit is detected, the defined **entry script** in the repository is automatically executed to apply the necessary updates or changes.

## Why Ansible Lite?

- **Simplicity**: No need for a dedicated Ansible server. The tool works directly with GitHub to monitor changes and automate tasks.

- **Lightweight**: Designed for environments that don't require heavy infrastructure.

- **Decentralization**: By leveraging GitHub, you can manage your configurations and updates in a simple and efficient way.

- **Automation through commits**: As soon as a commit is pushed to a monitored repository, the system can automatically trigger the entry script to apply the updates.

## Beta in Development

The **Ansible Lite** project is in beta and still under active development. We encourage users to test the tool and provide feedback via issues if any bugs or problems are encountered: [Open an issue](https://github.com/aidalinfo/ansible-lite/issues).
