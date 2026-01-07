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

Ubuntu currently provides the 24.04.1 LTS release. When new LTS versions are released, Ubuntu can be upgraded once the first point release is available. This can be done from the command line by using:
    `sudo do-release-upgrade`

Installation tips:
  - Search for "Turn Windows features on or off" in the Windows search bar and ensure that "Windows Subsystem for Linux" is turned on before restarting your machine.
  - To launch, use "ubuntu" on the command-line prompt or Windows Terminal, or click on the Ubuntu tile in the Start Menu.

For more information about Ubuntu WSL and how Canonical supports developers please visit:

https://ubuntu.com/wsl

## FAQ

### Unable to access internet

Check if you are able to access the internet using WSL e.g. Ubuntu profile:
```$ curl -v www.google.com```

Three options to try

#### Option 1

If unable to connect, run the following script that prevents the resolv.conf from being auto-generated:
```
sudo rm /etc/resolv.conf
sudo bash -c 'echo "nameserver 8.8.8.8" > /etc/resolv.conf'
sudo bash -c 'echo "[network]" > /etc/wsl.conf'
sudo bash -c 'echo "generateResolvConf = false" >> /etc/wsl.conf'
sudo chattr +i /etc/resolv.conf
```
#### Option 2

Turning Windows features on and off, when the name server is not “pingable”

1. Type "Turn Windows features on or off" in windows prompt, open the app 
1. Disable Linux subsystem in Windows features 
1. Disable Hyper-v (all subcomponents) 
1. Click "Ok" and follow to restart your machine
1. Enable Linux subsystem in Windows features 
1. Enable Hyper-v
1. Click "Ok" and follow to restart

#### Option 3

1. Open Powershell or Cmd as Administrator and run each of these commands:
   ```
   wsl --shutdown
   netsh winsock reset
   netsh int ip reset all
   netsh winhttp reset proxy
   ipconfig /flushdns
   ```
1. Hit the Windows Key, type `Network Reset` and hit enter.
1. Click "Reset now".
1. Restart Windows

If you're lucky, WSL 2 should now be able to `sudo apt-get update && sudo apt-get upgrade`.

Also see [No network connection in any distribution under WSL 2](https://github.com/microsoft/WSL/issues/5336#issuecomment-653881695)

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

