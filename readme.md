### How to clone a Git repo using SSH 
###### **Date:** Mon-28-Oct-2024

[My own Github repo](https://github.com/victoria-mckinney/ssh_keys)

##### [Gracious to the guidance provided in the linked article](https://graphite.dev/guides/git-clone-ssh-vs-https)


 *(optional)* [Create text file](https://hostman.com/tutorials/how-to-create-a-text-file-in-linux-terminal/) to store your keys (if necessary) in Terminal working directory: 

    >  touch <filename>.txt

In Terminal working directory:

    > ssh-keygen 

You should see online instructions for a passphase etc, ie: 


> 
        
        Enter file in which to save the key (ie Users/<useername>.ssh/id_edxxxxx): <filename>.txt
        Enter passphrase (empty for no passphrase): <passwordphrase>
        Enter same passphrase again: <passwordphrase>
        Your identification has been saved in <filename>.txt
        Your public key has been saved in <filename>.txt.pub
        The key fingerprint is:
        SHA256fdsfdsfssf:s6MNPlDRrB9cfl0suE7dfsfsfsdfsfsdfgoo9re+dHFuhwn87LVcFeewqewqwqLgNg
        The key's randomart image is:
        +--[EDXXXXX 256]--+
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


----
