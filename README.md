# Merry Action

**Merry Action** is a GitHub Action that simplifies the setup of a multi-chain testing environment using **Merry**. This action installs **Merry** natively on the GitHub Actions runner, allowing developers to easily launch and manage Bitcoin and Ethereum nodes for testing purposes.

## Features

- **Multi-Chain Support**: Quickly set up Bitcoin regtest and Ethereum localnet nodes in a single workflow.
- **Native Installation**: Installs **Merry** directly on the runner, making the command available for subsequent steps.
- **Dependency Management**: Automatically installs necessary dependencies like `curl` and `git`.
- **Easy Integration**: Simple to incorporate into your GitHub Actions workflows.

## Prerequisites

- Ensure you are using GitHub Actions in a repository that has the necessary permissions to run actions.
- The runner must support executing shell commands.

## Usage

To use **Merry Action** in your GitHub Actions workflow, follow these steps:

1. **Add this Action to Your Workflow**:

   Create or update your GitHub Actions workflow file (e.g., `.github/workflows/workflow_name.yml`) and include the following configuration:

   ```yaml
   jobs:
     setup-merry:
       runs-on: ubuntu-latest

       steps:
       - name: Set up Merry
         uses: catalogfi/merry-action@main
   ```

   You can confirm the installation by adding:

   ```yaml
   - name: Check Merry Version
     run: merry version
   ```

2. **Run Your Workflow**:

   Once you’ve added the action to your workflow, commit your changes and push to your repository. The action will execute, installing **Merry** and verifying its version.

## Commands

After setting up **Merry**, you can use various commands to manage your testing environment. Here are some commonly used commands:

- **Start Merry**: 
  ```bash
  merry go
  ```
- **Stop Merry**:
  ```bash
  merry stop
  ```
- **Get Logs**:
  ```bash
  merry logs -s <service>
  ```
- **Fund Accounts**:
  ```bash
  merry faucet <address>
  ```

Refer to the [Merry Documentation](https://merry.dev) for a full list of commands and their descriptions.
