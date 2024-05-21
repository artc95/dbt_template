# dbt_template

Steps on copying branch of one repo to another repo:
- `cd` i.e. change to directory where you want to make a copy of original repo
- `git clone --single-branch --branch <branch_name> <github_repo_url>` - to clone specific branch locally ([per stackoverflow](https://stackoverflow.com/questions/49290566/how-to-copy-only-single-branch-from-one-git-repo-to-another))
  - e.g. `git clone --single-branch --branch dbtCore_local https://github.com/arthurcht/dbtRepo.git` 
- `cd <copied repo name>` - to enter root directory of cloned branch ([per stackoverflow](https://stackoverflow.com/questions/49290566/how-to-copy-only-single-branch-from-one-git-repo-to-another))
  - e.g. `cd dbtRepo`   
- `git remote add <arbitrary name as reference to new repo> <github https path to new repo>` - to direct pushes to new repo
  - e.g. `git remote add dbt_template https://<path...>github.com/artc95/dbt_template.git`
  - if pushing from Visual Studio Code or Windows PowerShell (maybe other platforms too?), [personal access token must be created and added to github path](https://github.com/microsoft/vscode-pull-request-github/issues/3109) ... worked for Private repo, with repository permissions "Read access to metadata" and "Read and Write access to code"
  - if pushing to a **private** repo, must [generate](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) and [add](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) SSH public key to your Github account, and push using correct SSH key [(for Windows, create .ssh/config file to specify which SSH key to use)](https://stackoverflow.com/questions/71556140/git-does-not-use-ssh-key-windows)
- `git push <arbitrary name as reference to new repo> <name of cloned branch>` - branch name in new repo must match name of cloned branch!!! can always rename in new repo after pushing :)
  - e.g. `git push dbt_template dbtCore_local`
