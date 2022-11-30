# Git

## Configuring Your Developer Machine

- [How to use VS Code as your Git editor, difftool, and mergetool](https://www.roboleary.net/vscode/2020/09/15/vscode-git.html)
- `Shift + CMD + Period` shows hidden files in MacOS Finder
- `~/.gitconfig` is where your `--global` git settings are stored on MacOS

## Initial Source Control Setup

### Creating a New Repository on Github

> Note: when collaborating with a team only one team member. The "owner" of the Github repo will need to do the steps in this section.

1.  Open https://github.com/
1.  Sign-in
1.  In upper right corner click your `account icon`, then choose `Your Repositories`
1.  Click the green `New` button to create a new repository
1.  Fill in the `Repository name`. No spaces.
1.  Click the checkbox `Add a README file`
1.  Click the green button `Create Repository` at the bottom of the screen
1.  Copy the url for the repository to your clipboard

    1. Click in your browser's address bar and copy it
    1. Or click the green code button and then click the copy icon next to the URL

## Getting the Code

### Cloning a Github Repository to your Computer

> Note: all team members (owner as well as collaborators) will need to complete the steps in this section.

1.  Open a terminal in the directory where you want to work (usually LearnToCode)
    1. Windows: Right-click in Windows File Explorer and choose `Git Bash Here`
    1. MacOS: Right-click then choose `New Terminal at Folder`
       - Note if you are on an older MacOS version you may need to manually `cd` to the directory
1.  Clone the repository by running the following command.

    ```
    git clone https://github.com/yourusername/yourrepository.git
    ```

    > This will create a folder/directory inside of your work folder (Ex. LearnToCode/yourrepository) with your repository

    > If you get the following warning it means you forgot to "Click the checkbox `Add a README file`" in step 6 earlier.

    ```
    warning: You appear to have cloned an empty repository.
    ```

1.  Open your repository's corresponding folder/directory in VS Code

## Working on a Feature

### Create a Branch for Your Feature

1. After you've selected a feature to work on, create a branch in your local repo to build it in.
   - `$ git checkout -b username/short_description_of_feature`
1. Push the feature branch to the remote repo.
   - `git push --set-upstream origin username/short_description_of_feature`
1. Implement the requested feature. Make changes to your code (add files, edit files, delete files etc..). Test the feature.
1. Stage and then commit all changes in the new branch.
   - `git add .`
   - `git commit -m "feature completed"`
1. Push the feature branch to the remote repo.
   - `git push origin username/short_description_of_feature`

### Merge Other Changes into Your Feature

1. Checkout the main branch locally.
   - `$ git checkout main`
1. Pull down the main branch from GitHub to get the most up to date changes from others. If you practice git workflow as described here you should never have a merge conflict at this step.
   - `$ git pull origin main`
1. Test to make sure you have any changes others commited on main and then checkout your new feature branch.
   - `$ git checkout username/short_description_of_feature`
1. From your new feature branch, merge in your local main branch.
      > **Warning:** Running git merge with non-trivial uncommitted changes is discouraged: stage and commit your code before running the merge command below.
   - `$ git merge main`
     > **Tip:** You can always abort a failed merge and start over using the command
     - `$ git merge --abort`
1. Resolve any merge conflicts, test the feature on the new branch, and then commit all changes from the merge.
   - `$ git add .`
   - `$ git commit -m "Merge branch `main` into username/short_description_of_feature."`
1. Push the feature branch to the remote repo.
   - `git push origin username/short_description_of_feature`
1. Submit a pull request on GitHub asking to merge the branch into main.
1. The last steps should be completed frequently and repeatedly until the feature is complete.

## Integrate the Feature into the Remote Source Control Database

### Merging a Pull Request

> As a best practice, the team member who merges the code should never be the same person who wrote it. Let fresh eyes understand conflicts.

1. A teammate reviews another teammates code for quality and functionality.
1. The teammate merges the pull request back into the `main` branch by clicking the green `Merge pull request` button.
   Now all team members can pull it down and integrate it with any features they are completing.

   - Note: your teammate will often delete your branch from GitHub at this point but we **WILL NOT** so we can preserve the Git team collaboration steps.

## Resources

- [Pro Git Book from Apress](https://git-scm.com/book/en/v2)
- [Using Git with Visual Studio Code: The Ultimate Guide (2022)](https://yourbrainoncomputers.com/using-git-with-visual-studio-code-the-ultimate-guide/)
- [Git Branch Merging Best Practices](https://gist.github.com/calaway/ea880263b0c0495bb00ee877f001dc59)
