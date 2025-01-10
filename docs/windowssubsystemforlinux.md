# Windows subsystem for Linux (WSL)

The Windows Subsystem for Linux lets developers run a GNU/Linux environment (including most command-line tools, utilities, and applications) directly on Windows. Unmodified, without the overhead of a traditional virtual machine or dual boot setup.

https://www.youtube.com/watch?v=48k317kOxqg

## Setup

1. [Windows Terminal from Microsoft Store](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701)  
1. [Ubuntu from Microsoft Store](https://apps.microsoft.com/store/detail/ubuntu/9PDXGNCFSCZV)
  1. Add [Windows Terminal Raspberry Ubuntu theme](https://docs.microsoft.com/en-us/windows/terminal/custom-terminal-gallery/raspberry-ubuntu) to help identify Ubuntu profile.
1. aka.ms/wslusers
  1. [Set up a WSL development environment](https://aka.ms/wslusers)
  1. [Install WSL](https://docs.microsoft.com/en-us/windows/wsl/install)
  1. [Basic commands for WSL](https://docs.microsoft.com/en-us/windows/wsl/basic-commands)

## FAQ

### Installing CA certificates

!Verify whether these steps work

1. To install a custom certificate in Windows Subsystem for Linux (WSL), you can use the following steps:
1. Copy the certificate to a directory in your WSL environment. For example, you can copy the certificate to the `/usr/local/share/ca-certificates` directory.
1. Update the local certificate store with the new certificate. You can do this by running the following command: 
   ```
   sudo update-ca-certificates
   ```
1. This command will scan the `/usr/local/share/ca-certificates` directory for new certificates and will add them to the local certificate store.
1. Restart any applications that need to use the new certificate, such as your web browser.
1. To verify that the certificate has been installed correctly, you can use the command below. It should display the details of the certificate you just installed. 
   ```
   sudo openssl s_client -connect <hostname>:<port> -CAfile /etc/ssl/certs/ca-certificates.crt
   ```

It's important to keep in mind that this process can be different depending on the distribution and the version that you are using in WSL, but it should be similar.

Also you could keep in mind to use CA signed certificates. Custom self-signed ones can be not fully trusted.

