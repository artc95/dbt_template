# dbt_template

Steps on copying branch of one repo to another repo:
- `git clone --single-branch --branch <branch_name> <github_repo_url>` - to clone specific branch locally ([per stackoverflow](https://stackoverflow.com/questions/49290566/how-to-copy-only-single-branch-from-one-git-repo-to-another))
  - e.g. `git clone --single-branch --branch dbtCore_local https://github.com/arthurcht/dbtRepo.git` 
- `cd <copied repo name>` - to enter root directory of cloned branch ([per stackoverflow](https://stackoverflow.com/questions/49290566/how-to-copy-only-single-branch-from-one-git-repo-to-another))
  - e.g. `cd dbtRepo`   
- `git remote add <arbitrary name as reference to new repo> <github https path to new repo>` - to direct pushes to new repo
  - e.g. `git remote add dbt_template https://<path...>github.com/artc95/dbt_template.git`
  - if pushing from Visual Studio Code, [personal access token must be created and added to github path](https://github.com/microsoft/vscode-pull-request-github/issues/3109) ... worked for Private repo, with repository permissions "Read access to metadata" and "Read and Write access to code"
- `git push <arbitrary name as reference to new repo> <name of cloned branch>` - branch name in new repo must match name of cloned branch!!! can always rename in new repo after pushing :)
  - e.g. `git push dbt_template dbtCore_local`
