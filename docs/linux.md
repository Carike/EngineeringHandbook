# Linux

## Basic commands
* List files and folders
  * `ls` - Lists all files and directories in the present working directory
  * `ls -R` - Lists files in sub-directories as well
  * ```ls -a``` - Lists hidden files as well
  * ```ls -al``` - Lists files and directories with detailed information like permissions,size, owner, etc.
* Working with directories
  * `cd` or `cd ~` - Navigate to HOME directory
  * `cd ..` - Move one level up
  * `cd` - To change to a particular directory
  * `cd /` - Move to the root directory
  * `mkdir directoryname` - Creates a new directory in the present working directory or a at the specified path
  * `rmdir` - Deletes a directory
  * `mv` - Renames a directory
* Working with files
  * `cat > filename` - Creates a new file
  * `cat filename` - Displays the file content
  * `cat file1 file2 > file3` - Joins two files (file1, file2) and stores the output in a new file (file3)
  * `mv file "new file path"` - Moves the files to the new location
  * `mv filename new_file_name` - Renames the file to a new filename
  * `rm filename` - Deletes a file
* Other commands
  * `sudo` - Allows regular users to run programs with the security privileges of the superuser or root
  * `man` - Gives help information on a command
  * `history` - Gives a list of all past commands typed in the current terminal session
  * `clear` - Clears the terminal
  * `pr -x` - Divides the file into x columns
  * `pr -h` - Assigns a header to the file
  * `pr -n` - Denotes the file with Line Numbers
  * `lp -nc , lpr c` - Prints “c” copies of the File
  * `lp-d lp-P` - Specifies name of the printer
  * `apt-get` - Command used to install and update packages
  * Command to send email
    * ```
      mail -s 'subject'
      -c 'cc-address'
      -b 'bcc-address'
      'to-address'
      ```
  * Command to send email with attachment
    * ```
      mail -s "Subject"
      to-address < Filename
      ```
* Usefull commands
  * `for (( ; ; )); do telnet 10.10.0.1 443; done;` - Run a continuous telnet test against the target 

## Using SSH

Used for secure terminal connections to Linux servers

### Generate SSH key

Useful links:
1. [Create an SSH key pair](https://learn.microsoft.com/en-us/viva/glint/setup/sftp-ssh-key-gen)
1. [Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
1. [Generating Your SSH Public Key](https://git-scm.com/book/pt-pt/v2/Git-no-Servidor-Generating-Your-SSH-Public-Key)
1. [Key-based authentication in OpenSSH for Windows](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement)
1. [Get started with OpenSSH for Windows](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui&pivots=windows-server-2025)

### Connecting to machine

[Connect using SSH] (https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/factoryos/connect-using-ssh?view=windows-11#connect)

1. Open your terminal (Ubuntu preferably)
1. Enter the user and machine’s IP address you wish to connect to ```ssh loginname@10.10.0.1```
1. If it’s the first time you are connecting to the server you need to accept that you trust the host
1. You will then note the change in the terminal once you have successfully logged on.

### FAQ

1. [How to Fix SSH Failed Permission Denied](https://phoenixnap.com/kb/ssh-permission-denied-publickey)

## Tips and tricks

1. [How To Use Linux Screen](https://linuxize.com/post/how-to-use-linux-screen/)
1. Uncomplicated Firewall (UFW)
   1. [How to Set Up a Firewall with UFW on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-with-ufw-on-ubuntu)
   1. [UFW Essentials: Common Firewall Rules and Commands](https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands)