# GIT

## Installation
Git for Windows. Download the installer from https://git-scm.com/download/win.

## Configuration

### Configure credentials

### Proxy

1. Open CMD and enter following commands:
   ```
   git config --global http.proxy http://[proxy.URL.com]:8080
   git config --global https.proxy http://[proxy.URL.com]:8080
   ```
1. Use there commands to confirm that it is running:
   ```
   git config --global --get http.proxy
   git config --global --get https.proxy
   ```
1. Unset the configuration by using these commands
   ```
   git config --global --unset http.proxy
   git config --global --unset https.proxy
   ```

## Learn more

1. Git Book free
1. GitHub Foundations certification
1. Microsoft Learn