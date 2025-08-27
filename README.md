# GitLab Runner installation guide for Windows

----------

# 🛠️ Install GitLab Runner on Windows

**Tiers Supported:** Free, Premium, Ultimate  
**Offerings:** GitLab.com, GitLab Self-Managed, GitLab Dedicated

----------

## ⚙️ Prerequisites

-   [Git](https://git-scm.com/) installed from the official site
-   A password for your user account (if not using the Built-in System Account)
-   System locale set to **English (United States)** to avoid character encoding issues
    -   See [issue 38702](https://gitlab.com/gitlab-org/gitlab-runner/-/issues/38702) for more info

----------

## 📦 Installation Steps

### 1. Create a Directory

Create a folder, e.g.:

```text
C:\GitLab-Runner

```

### 2. Download the Binary

-   Download the [64-bit or 32-bit binary](https://gitlab-runner-downloads.s3.amazonaws.com/latest/index.html)
-   Place it in the folder you created
-   (Optional) Rename the binary to:

```text
gitlab-runner.exe

```

> 🔐 **Security Tip:** Restrict Write permissions on the GitLab Runner directory and executable to prevent privilege escalation.

----------

## 🖥️ Register and Install the Runner

Open an **elevated command prompt** and follow the steps below.

### 🔧 Register a Runner

Follow GitLab's [runner registration guide](https://docs.gitlab.com/runner/register/index.html).

----------

## 🚀 Install GitLab Runner as a Service

### Option 1: Run as Built-in System Account (Recommended)

```powershell
cd C:\GitLab-Runner
.\gitlab-runner.exe install
.\gitlab-runner.exe start

```

### Option 2: Run as User Account

> You must enter a valid password for the current user account.

```powershell
cd C:\GitLab-Runner
.\gitlab-runner.exe install --user ENTER-YOUR-USERNAME --password ENTER-YOUR-PASSWORD
.\gitlab-runner.exe start

```

----------

## 🛠️ Optional Configuration

-   Edit `C:\GitLab-Runner\config.toml` to:
    -   Increase `concurrent` value for parallel jobs
    -   Change shell executor to **Bash** or **PowerShell** instead of default **Batch**

----------

## 🧩 Troubleshooting

If you encounter issues, refer to the [GitLab Runner troubleshooting guide](https://docs.gitlab.com/runner/troubleshooting/index.html).
