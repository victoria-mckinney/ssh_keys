### How to clone a Git repo using SSH:

##### [Gracious to the guidance provided in the linked article](https://graphite.dev/guides/git-clone-ssh-vs-https)

###### **Date:** Mon-28-Oct-2024

 *(optional)* [Create text file](https://hostman.com/tutorials/how-to-create-a-text-file-in-linux-terminal/) to store your keys (if necessary) in Terminal working directory: 

    >  touch text.txts

In Terminal working directory:

    > ssh-keygen 

You should see online instructions for a passphase etc, ie: 


> 
        
        Enter file in which to save the key (/Users/<username>/.ssh/id_ed25519): text.txt    
        Enter passphrase (empty for no passphrase): 
        Enter same passphrase again: 
        Your identification has been saved in text.txt
        Your public key has been saved in text.txt.pub
        The key fingerprint is:
        SHA256:s6MNPlDRrB9cfl0suE7goo9re+dHFuhwn87LVcFLgNg victoriamckinney@Victoria’s MacBook Air
        The key's randomart image is:
        +--[ED25519 256]--+
        |       o  o .o . |
        |      . o.oE. + o|
        |       + + o o * |
        |      o = = = o o|
        |     . oS* = o ..|
        |    . . .o. *  . |
        |     ..oo  =  .  |
        |     .++o...+.   |
        |     .==.o..o.   |

If you open the *text.txt* file (or whatever you have named it): you will see something like the following:

        -----BEGIN OPENSSH PRIVATE KEY-----
        b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
        QyNTUxOQAAACCNY/+maty4mamQOcEOW31cExoZgjUakXw73PgJnbX5bAAAALCeAnvangJ7
        2gAAAAtzc2gjdeufheuifhWQyNTUxOQAAACCNY/+maty4mamQOcEOW31cExoZgjUakXw73PgJnbX5bA
        AAAEBNVQ6T5KCW7ZEzxNwhfwehRXAWP3Y1j/6Zq3LiZqZA5wQ5bfVwT
        GhmCNRqRfDejhfewiuhfeiuAAAKXZpY3RvcmlhbWNraW5uZXlAVmljdG9yaWHigJlzIE1hY0
        Jvb2sgQWlyAQIDBA==
        -----END OPENSSH PRIVATE KEY-----
