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

1. [Pro Git](https://git-scm.com/book/en/v2) free book
1. [GitHub Foundations certification](https://learn.microsoft.com/en-za/training/paths/github-foundations/)
1. [Introduction to Git](https://learn.microsoft.com/en-za/training/modules/intro-to-git/) on Microsoft Learn

## Links

- [Git and GitHub essentials for Microsoft Learn documentation](https://learn.microsoft.com/en-us/contribute/content/git-github-fundamentals)