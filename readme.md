# How to SSH Github to Push a Repository

## Steps to SSH github

1. From Terminal, create SSH Key Pair

``` bash
ssh-keygen -t rsa -C "<username>@github.com"
```

`username` is your Github Username.

2. From the above command, will creates 2 files in your home directory or `~/.ssh/` folder, `id_rsa` and `id_rsa.pub`. Open `id_rsa.pub` file and copy all of its content. From terminal you can use either of this 2 commands.
``` bash
cat ~/.ssh/id_rsa.pub
```
or
```bash
nano ~/.ssh/id_rsa.pub
```

3. Paste the Public Key on Github, User --> Settings --> SSH and GPG keys --> New SSH key. Add descriptive title and paste the Key on Key field. Then, Add SSH key to save.

## Steps to Push a Repository

> If the repository have been created and committed, by these steps:
``` bash
git init
git add .
git commit -m "commit message"
```
then we need to create user configuration.

1. Configure git user.
``` bash
git config --global user.email "<username>@github.com"
git config --global user.name "Your Name in Github"
```
> Git user configuration is one time setting on a machine.

2. Remote Github repository.
```bash
git remote add origin git@github.com:<username>/<repository>.git
```

3. Change to remote repository branch, then push local repository to remote repository.
```bash
git branch -M main
git push -u origin main
```

## Sources
- [Public Key Git Error - Github](https://gist.github.com/adamjohnson/5682757)
- Quick Setup - Github, on newly created repository.