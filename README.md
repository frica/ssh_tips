## Get rid of the passphrase request every time

Start ssh-agent if not started:

    $ eval `ssh-agent -s`

Add your private key using ssh-add

    $ ssh-add ~/.ssh/id_rsa_key  
    Enter passphrase for /home/user/.ssh/id_rsa_key:  
    Identity added: /home/user/.ssh/id_rsa_key 
    (/home/user/.ssh/id_rsa_key)  

Check if the key is added (parameter is a lowercase L):

    $ ssh-add -l  
    2048 55:96:1a:b1:31:f6:f0:6f:d8:a7:49:1a:e5:4c:94:6f  
    /home/user/.ssh/id_rsa_key (RSA)

Try to connect to your Git server:

    $ ssh git.example.com

Now you can use Git without extra passphrase prompts.

See [thread](https://superuser.com/questions/988185/how-to-avoid-being-asked-enter-passphrase-for-key-when-im-doing-ssh-operatio)

## Get rid of the password / Github token requests

In the /myrepo/.git, make sure you point to 

    url = git@github.com:user/myrepo.git

and not:

    url= https://github.com/user/myrepo.git

## Github CLI

Available with snap on Ubuntu WSL

See also: [GitHub CLI page](https://cli.github.com/manual/gh_auth_login)
