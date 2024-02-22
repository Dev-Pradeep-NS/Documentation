## Initialize the local directory as a Git repository.
    git init
## Rename your local master branch into main if necessary
    git branch -m main
## Add files
    git add .
## Commit your changes
    git commit -m "initial commit"
## Add remote origin
    git remote add origin <Remote repository URL>
## Verifies the new remote URL
    git remote -v
## Push your changes to main branch
    git push -u -f origin main
