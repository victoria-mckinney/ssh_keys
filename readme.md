### How to securely clone a Git repo using SSH 
###### **Date:** Mon-28-Oct-2024

[Associated Github repo](https://github.com/victoria-mckinney/ssh_keys)
##### [Gracious to the guidance provided in the linked article](https://graphite.dev/guides/git-clone-ssh-vs-https)

------
##### 1. Generate Key


 *(optional)* [Create text file](https://hostman.com/tutorials/how-to-create-a-text-file-in-linux-terminal/) to store your keys (if necessary) in Terminal working directory: 

    >  touch <filename>.txt

In Terminal working directory:

    > ssh-keygen 

You should see online instructions for a passphase etc, ie: 


> 
        
        Enter file in which to save the key (~username/repo_folder_/ssh/id_edxxxxx): <filename>.txt
        Enter passphrase (empty for no passphrase): <passwordphrase>
        Enter same passphrase again: <passwordphrase`>
        Your identification has been saved in <filename>.txt
        Your public key has been saved in <filename>.txt.pub
        The key fingerprint is:
        SHA256fdsfdsfssf:s6MNPlDRrB9cfl0suE7dfsfsfsdfsfsdfgoo9re+dHFuhwn87LVcFeewqewqwqLgNg
        The key's randomart image is:
        +--[ED25519 256]--+
        |       o  o .o . |
        |      . o.oE. + o|
        |     . oS* = o ..|
        |    . . .o. *  . |
        |     ..oo  =  .  |
        |     .++o...+.   |
        |     .==.o..o.   |

If you open the *<filename>.txt* file (or whatever you have named it): you will see something like the following:

        -----BEGIN OPENSSH PRIVATE KEY-----
        b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
        QyNTUxOQAAACCNY/+maty4mamQOcEOW31cExoZgjUakXw73PgJnbX5bAAAALCeAnvangJ7
        2gAAAAtzc2gjdeufheuifhWQyNTUxOQAAACCNY/+mafdfssty4mamQOcEOW31cExoZgjUakXw73PgJnbX5bA
        GhmCNRqRfDejhfewiuhfeiuAAAKXZpY3RvcmlhbWNraW5uZXlAVmljdG9yaWHigJlzIE1hY0
        Jvb2sgQWlyAQIDBA==
        -----END OPENSSH PRIVATE KEY-----


------
##### 2. Starting the SSH agent:

        > eval "$(ssh-agent -s)"

Output: 
        
        > Agent pid xxxxx

------
##### 3. Configuring SSH to use the SSH agent (macOS Sierra 10.12.2 or later):

1. **Check if the SSH config file exists:** Use open *~/.ssh/config* to see if the file exists. If it doesn't, you will need to create it.

2. **Create the SSH config file if necessary:** Use *touch ~/.ssh/config* to create the file.

3. **Open the config file:** You can use a text editor to open the file, e.g., *vim ~/.ssh/config*

4. **Modify the config file:** Add the following lines to the file, adjusting the *IdentityFile* path if your SSH key has a different name or location:

                Host github.com
                AddKeysToAgent yes
                UseKeychain yes
                IdentityFile ~/.ssh/id_edxxxxx

> **Note:** If you didn't set a passphrase for your key, omit the *UseKeychain* *yes* line. If you encounter a configuration error, try adding *IgnoreUnknown UseKeychain* under a specific Host definition.

----

##### 4. Adding your SSH key to the SSH agent: 

1. Add your SSH private key to the ssh-agent: Use the following command, ensuring to replace id_edXXXX with the name of your key.
   


        ssh-add --apple-use-keychain ~/.ssh/id_edxxxxx


   This adds your SSH key to the ssh-agent and stores your passphrase in the keychain, making it so you don't have to enter the passphrase every time the key is used.

        Enter passphrase for id_edxxxxx.txt:  <enter passphrase you set in first step above (if applicable)>
        Identity added: id_edxxxxx.tx

> **Note:** The *-apple-use-keychain* option helps store the passphrase in your keychain when adding an SSH key to the ssh-agent. If you do not have a passphrase or are not using an Apple device, adjust the command accordingly.

----

##### 5. Clone the repository:
   
1. Find the SSH URL of the repository and run: 
                
        git clone git@github.com:user/repository.git

Make sure to replace **github.com:user/repository.git** with the actual path to your repository.


---
