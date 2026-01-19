# ud - Conditional Debian & WSL Maintenance Utility

A technically precise Bash script designed to automate system maintenance for Debian 13 (Trixie) and WSL environments. This utility prioritizes logic and efficiency by performing conditional upgrades only when upstream changes are detected.

## Features:

* **Metadata Synchronization:** Updates local package indexes to ensure repository parity.

* **Conditional Execution:** Dynamically checks for available upgrades; if the system is current, the upgrade process is bypassed to conserve resources.

* **Minimalist Cleanup:** Automatically purges orphaned libraries and redundant dependencies via autoremove.

* **Platform Aware:** Explicitly documented for cross-compatibility between native Debian and Windows Subsystem for Linux.

## Installation & Usage:

To integrate this into your workflow:

1. **Place the script in your preferred script directory (e.g., ~/bash_scripts/).**

2. **Ensure the file is executable:**

    ```bash
    chmod +x ud

3. **Add to your shell profile:** Append the following line to your ~/.bashrc (or ~/.zshrc if applicable):

    ```bash
    export PATH="$PATH:$HOME/bash_scripts"

4. **Refresh your shell:**

    ```bash
    source ~/.bashrc

5. **Execute the script:** 

    ```bash
    ud

## Script Metadata:

* **Author:** David (Davo) Faulkner

* **Target OS:** Debian-based distributions, WSL

* **Logic Flow:** Update -> Check (if Upgradable) -> Upgrade (Conditional) -> Autoremove
