# ud - Conditional Debian & WSL Maintenance Utility

A technically precise Bash script designed to automate system maintenance for **Debian 13 (Trixie)** and **WSL** environments. This utility prioritizes logic and efficiency by performing conditional upgrades only when upstream changes are detected.

## Features
* **Bash Strict Mode:** Utilizes `set -euo pipefail` to ensure the script exits immediately on any command errors, undefined variables, or pipeline failures.
* **Numerical Delta Detection:** Uses numerical package counting (`grep -c`) to determine upgrade status, ensuring high reliability and logic-driven execution.
* **Conditional Execution:** Dynamically compares the update status string; if the system is current, the upgrade process is bypassed to conserve resources.
* **Auditability:** Redirects verbose output from the upgrade and cleanup phases to dedicated log files (`upgrade_log.txt` and `autoremove_log.txt`) located in a managed log directory along with `update_log.txt` at `~/ud_logs`.
* **Minimalist Cleanup:** Automatically purges orphaned libraries and redundant dependencies.

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

* **Logic Flow:** Strict Mode Init -> Log Dir Validation -> Update & Log -> Conditional Check (if Upgradable) -> Upgrade & Log -> Autoremove & Log
