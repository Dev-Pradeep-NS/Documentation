## How to connect Jenkins with GitHub using SSH?(Everything is done in Ubuntu 22.04)
### Generate SSH Key Pair
    ssh-keygen -t ed25519 -C "your_email@example.com"
### Copy the SSH public key to your clipboard and add it in GitHub.
    cat ~/.ssh/id_ed25519.pub
### Test your SSH Connection in Ubuntu
    ssh -T git@github.com
### Configure Jenkins to Use SSH Key and salesforce cli
##### switch to the jenkins user
    sudo -su jenkins
##### Copy the SSH key to your clipboard and add it in Jenkins credentials
    cat ~/.ssh/id_ed25519
##### Test your SSH Connection
    ssh -T git@github.com