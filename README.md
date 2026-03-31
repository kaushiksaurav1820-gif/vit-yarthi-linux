# vit-yarthi-linux

## Open Source Audit — Python
**Course:** Open Source Software (OSS NGMC)  
**Student:** Saurav  
**Roll Number:** 24BSA10300  
**Software Audited:** Python (CPython)  
**License Audited:** Python Software Foundation License v2 (PSF-2.0)

---

## Project Overview

This repository contains the complete submission for the Open Source Audit capstone project. The project audits Python — one of the world's most widely used open-source programming languages — covering its origin story, license analysis, ethical reflection, Linux footprint, FOSS ecosystem, and a comparison with its proprietary alternative (MATLAB).

Five shell scripts accompany the report to demonstrate practical Linux and shell scripting skills.

---

## Repository Contents

```
oss-audit-24MIM10210/
├── README.md
├── scripts/
│   ├── script1_system_identity.sh      # System info welcome screen
│   ├── script2_foss_inspector.sh       # Package install checker with case statement
│   ├── script3_disk_auditor.sh         # Directory permission and disk usage auditor
│   ├── script4_log_analyzer.sh         # Log file keyword counter and analyzer
│   └── script5_manifesto_generator.sh  # Interactive open-source manifesto generator
```

The project report PDF is submitted separately on the VITyarthi portal.

---

## Script Descriptions

### Script 1 — System Identity Report (`script1_system_identity.sh`)
Displays a formatted welcome screen showing the Linux distribution, kernel version, architecture, current user, home directory, system uptime, date/time, and the open-source license covering the OS and Python.

**Concepts used:** Variables, `echo`, command substitution `$()`, string formatting, conditional file check.

### Script 2 — FOSS Package Inspector (`script2_foss_inspector.sh`)
Checks whether a specified FOSS package (default: `python3`) is installed using either RPM or dpkg/apt, displays version and license information, and prints a philosophical note about the package using a `case` statement.

**Concepts used:** `if-then-else`, `case` statement, `rpm -qi`, `dpkg -s`, pipe with `grep`, command-line arguments `$1`.

### Script 3 — Disk and Permission Auditor (`script3_disk_auditor.sh`)
Loops through standard Linux system directories and Python-specific directories, reporting permissions, owner, group, and disk usage for each. Also locates and displays the Python interpreter's real path by resolving symlinks.

**Concepts used:** `for` loop, arrays, `ls -ld`, `du -sh`, `awk`, `cut`, `readlink`, conditional `-d` and `-e` tests.

### Script 4 — Log File Analyzer (`script4_log_analyzer.sh`)
Reads a log file line by line, counts how many lines contain a specified keyword (default: `error`), calculates match percentage, and displays the last 5 matching lines. Includes retry logic to suggest alternative log files if the specified file is not found.

**Concepts used:** `while read` loop, `if-then`, counter variables, command-line arguments `$1` and `$2`, `grep`, `tail`, here-string `<<<`.

### Script 5 — Open Source Manifesto Generator (`script5_manifesto_generator.sh`)
Interactively asks the user three questions and generates a personalised open-source philosophy statement, saving it to a `.txt` file named after the current user. Demonstrates alias creation and expansion.

**Concepts used:** `read` for user input, string concatenation, file writing with `>` and `>>`, `date` command, `alias` and `shopt -s expand_aliases`, validation with `-z`.

---

## How to Run the Scripts on Linux

### Prerequisites
- A Linux system (Ubuntu, Debian, RHEL, CentOS, Fedora, or compatible)
- Bash shell (version 4+): verify with `bash --version`
- Python3 installed: `python3 --version`
- Standard Unix utilities: `ls`, `du`, `grep`, `awk`, `cut`, `date` (all pre-installed on any Linux)

### Step 1 — Clone the repository
```bash
git gh repo clone Varun786223/oss-audit-24MIM10210
cd oss-audit-24MIM10210
```

### Step 2 — Make scripts executable
```bash
chmod +x scripts/*.sh
```

### Step 3 — Run each script

**Script 1 — System Identity Report:**
```bash
./scripts/script1_system_identity.sh
```

**Script 2 — FOSS Package Inspector:**
```bash
# Check python3 (default)
./scripts/script2_foss_inspector.sh

# Check a specific package
./scripts/script2_foss_inspector.sh git
./scripts/script2_foss_inspector.sh firefox
```

**Script 3 — Disk and Permission Auditor:**
```bash
./scripts/script3_disk_auditor.sh
```
> Note: Some directories (like `/root`) may show "permission denied" for disk size — this is expected. Run with `sudo` for complete output.

**Script 4 — Log File Analyzer:**
```bash
# Ubuntu/Debian
./scripts/script4_log_analyzer.sh /var/log/syslog error

# RHEL/CentOS
./scripts/script4_log_analyzer.sh /var/log/messages error

# Custom keyword
./scripts/script4_log_analyzer.sh /var/log/syslog warning
```
> Note: Log files require read permission. Run with `sudo` if you see permission errors.

**Script 5 — Open Source Manifesto Generator:**
```bash
./scripts/script5_manifesto_generator.sh
```
Follow the three prompts. Your manifesto will be saved as `manifesto_<username>.txt` in the current directory.

---

## Dependencies

All scripts rely only on standard Unix/Linux utilities that are pre-installed on any Linux distribution:

| Utility | Purpose | Pre-installed? |
|---------|---------|---------------|
| `bash` | Shell interpreter | Yes |
| `uname` | Kernel/arch info | Yes |
| `whoami`, `hostname` | User/host info | Yes |
| `date` | Date and time | Yes |
| `ls`, `du` | File/disk info | Yes |
| `grep`, `awk`, `cut` | Text processing | Yes |
| `rpm` or `dpkg` | Package info | Yes (distro-dependent) |
| `python3` | Script 2 version check | Required for Python audit |

No external libraries or pip packages are required to run any script.

---

## Software Audited

**Python** — developed by Guido van Rossum, first released publicly in February 1991.  
**License:** Python Software Foundation License v2 (PSF-2.0)  
**Source code:** https://github.com/python/cpython  
**License text:** https://docs.python.org/3/license.html  
**Governing body:** Python Software Foundation (https://www.python.org/psf/)

---

*Submitted as part of the OSS NGMC Capstone Project | VIT | 2026–27*
