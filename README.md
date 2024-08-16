# Access Multiple Github Account from one system.
### Accounts with username on github.com:
    1.account1-username
    2.account2-username

### ssh key on your system (use ssh-keygen to generate the keys, ssh-add to add the keys)
    1. id_rsa         for account1-username          (ssh-keygen -C "your_email@example.com")
    2  id_ed25519     for account2-username          (ssh-keygen -t ed25519 -C "your_email@example.com")


### create config file in folder .ssh with name config 

### add these to your config file .ssh/config
    Host account1
    HostName github.com
    IdentityFile ~/.ssh/id_rsa                   # add path to your private key for account1-username


    Host account2
    HostName github.com
    IdentityFile ~/.ssh/id_ed25519               # add path to your private key for account2-unsername

### clone your repository with respective accounts (using git clone git@<Host>:username.git)

    1. For account1-username having repo  ssh link  -> git@github.com:account1-username/repo.git
        a. replace github.com with Host in config file with respective account, for account1-username -> account1
        > git clone git@account1:account1-username.git

    2. For account2-username haveing repo ssh link -> git@github.com:account2-username/repo.git
        a. replace github.com with Host in config file with respective account, for account2-username -> account2
        > git clone git@account2:account2-username.git


### after cloning you don't need to worry about key
