# Celerenv

Celerenv is a CLI tool designed to streamline the setup and management of Python environments with **Poetry**, **gcloud**, and other dependencies necessary for development in CELERO.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Available Commands](#available-commands)
- [Uninstallation](#uninstallation)
- [Prerequisites](#prerequisites)
- [References](#references)

## Installation

To install `celerenv`, run the following command:

```bash
wget -qO- https://raw.githubusercontent.com/maicondmenezes-at-celero/celerenv/bin/install | sudo bash
```

This command downloads the installation script, configures the environment, and creates a symlink to make the `celerenv` command available globally.

## Usage

After installation, you can use the `celerenv` command to manage your Python development environment.

```bash
celerenv <command>
```

## Available Commands

Below is a list of available commands you can run with `celerenv`:

- `pre-setup`:
  - Performs a pre-setup for the Poetry environment, installing Poetry and setting up dependencies.
  
- `setup`:
  - Installs project dependencies using Poetry.
  
- `local-setup`:
  - Sets up the local development environment with Google Cloud SDK credentials. Requires the user to have `gcloud` installed and configured.
  
- `glog`:
  - Logs into Google Cloud SDK (`gcloud auth login` and `gcloud auth application-default login`).
  
- `venv_clean`:
  - Cleans the Python virtual environment by removing the `.venv` directory and the `poetry.lock` file.
  
- `venv`:
  - Creates and activates a new Python virtual environment.
  
- `predev`:
  - Performs pre-development setup, including Google Cloud login, virtual environment setup, and local setup for development.
  
- `uninstall`:
  - Uninstalls the `celerenv` CLI and removes all related files.

## Uninstallation

To completely uninstall `celerenv` from your system, simply run:

```bash
celerenv uninstall
```

This will remove the symbolic link from `/usr/local/bin` and delete the `~/.celerenv` directory where the tool was installed.

## Prerequisites

In order for `celerenv` to work correctly, the following prerequisites must be met:

- **Python 3**: Ensure Python 3 is installed and available in your system's `PATH`.
  
- **Poetry**: `Poetry` is a tool for dependency management and packaging in Python. It is installed automatically during the pre-setup, but you can install it manually by running:
  
  ```bash
  curl -sSL https://install.python-poetry.org | python3 -
  ```
  
- **Google Cloud SDK (`gcloud`)**: If you plan to use the `local-setup` or `glog` commands, you must have the Google Cloud SDK installed. Follow the installation guide [here](https://cloud.google.com/sdk/docs/install).

- **Pip**: Ensure that you have `pip` installed and updated. This can be done with the following command:
  
  ```bash
  sudo apt install python3-pip
  pip install --upgrade pip
  ```

- **Keyring & Google Artifact Registry Auth**: These are additional dependencies used by `celerenv` for authentication with Google Cloud. They are installed automatically during setup.

  You can install them manually with:
  
  ```bash
  pip install keyring keyrings.google-artifactregistry-auth
  ```

## References

Here are some useful references for the tools used in `celerenv`:

- [Poetry Documentation](https://python-poetry.org/docs/)
- [Google Cloud SDK Documentation](https://cloud.google.com/sdk/docs)
- [Keyring Python Package](https://pypi.org/project/keyring/)
- [Google Artifact Registry Auth Keyring](https://cloud.google.com/artifact-registry/docs/python/quickstart)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
