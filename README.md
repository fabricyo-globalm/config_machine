# config_machine

### Git SSH Connection
https://medium.com/@akhigbeeromo/why-git-keeps-asking-for-your-password-even-after-setting-up-ssh-and-how-i-fixed-it-3cd65a83d462
```bash
ssh-keygen -t ed25519 -C "you@example.com"
```
  A custom file location
  ```bash
    ~/.ssh/id_ed25519_personal
  ```
#### Add ssh to agent
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519_personal
```
#### Add ssh key to github
```bash
cat ~/.ssh/id_ed25519_personal.pub
```
#### Config SSH file
```bash
nano ~/.ssh/config
```
```text
# Personal GitHub
Host github-personal
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519_personal
  IdentitiesOnly yes
```

#### Remote not set yet
```git remote add origin git@github-personal:<YOUR_REPO_NAME>/your-repo.git```
#### Remote already set
```git remote set-url origin git@github-personal:<YOUR_REPO_NAME>/your-repo.git```

#### Test
```ssh -T git@github-personal```



### VS Code alias in terminal MACOS
```bash
open ~/.zshrc
alias code='open -a "Visual Studio Code"' # open file or folder in VSCode e.g. code ~/.zshrc
```
