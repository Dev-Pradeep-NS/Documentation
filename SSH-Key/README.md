### About SSH
Using the SSH protocol, you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username and personal access token at each visit. You can also use an SSH key to sign commits.
### Benefits of SSH Authentication 🔒
#### Enhanced Security: SSH key pairs are more challenging to crack compared to traditional passwords.
#### Seamless Integration: Automate pull/build processes without password prompts.
#### Accountability: Easily track which systems access your repositories.
### Generating a new SSH key
    ssh-keygen -t ed25519 -C "your_email@example.com"
### Copy the SSH public key to your clipboard and add it in GitHub.
    pbcopy < ~/.ssh/id_ed25519.pub
if pbcopy is not working you can go to .ssh folder, open the file in text editor and copy it
### Test your SSH Connection in Linux
    ssh -T git@github.com