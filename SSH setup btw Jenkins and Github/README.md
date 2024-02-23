## How to connect Jenkins with GitHub using SSH?(Everything is done in Ubuntu 22.04)
### switch to the jenkins user
    sudo -su jenkins
### Generate SSH Key Pair
    ssh-keygen -t ed25519 -C "your_email@example.com"
### Copy the SSH public key to your clipboard and add it in GitHub.
    cat ~/.ssh/id_ed25519.pub
### Copy the SSH key to your clipboard and add it in Jenkins credentials
    cat ~/.ssh/id_ed25519
### Test your SSH Connection
    ssh -T git@github.com