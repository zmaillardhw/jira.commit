## JIRA Ticket Git Hook

#### Installation
1. Copy contents of .git-template into your home directory
2. Modify `.git-template/hooks/prepare-commit-msg` to be executable.
  a. `chmod a+x ~/.git-template/hooks/prepare-commit-msg`
3. Update your global `.gitconfig` file to include the template directory in the init section.  Ensure the path is correct.  The global `.gitconfig` file typically is in the home directory.
```
[init]
    templatedir = /home/yourhomedir/.git-template/
```
4. Re-run `git init` within the repository to enable feature.
```bash
cd ~/myawesome.repo
git init
```

#### Usage
1. Ensure branch name has the JIRA Ticket number in it.
2. Create a commit.  The commit message will prepend the ticket number to the start of the commit (in square brackets).
3. If you create a commit using the `-m` flag, the ticket number will automatically be pre-pended.
```bash
git commit -am "My Awesome Changes"
### Resulting Git Commit Message on branch CLN-123_awesome_change
### [CLN-123] My Awesome Change
```

#### Limitations
1. Only tested on WSL
2. Valid JIRA Ticket Names Hardcoded.  Currently supports CLN, PT, and NTG.
