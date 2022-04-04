# Version control with git

*Copyright notice: all these notes have been taken collaboratively in class during the lecture. Everyone is an author.*

## Introduction


`Git` is a version control tool, which basically keeps track of changes. When a change is pushed, git removes/replaces/adds only the changed lines. Everyone has a full copy of the entire git tree, that is everything. The best way to learn git is to just do it. Just try, and you will learn as you go. The nice thing with git is that all the changes are saved, so if you screw up it is always possible and easy to go back...

### Why version control?

 - History
   - The contributors (`git blame`)
   - The actual code changes
   - Go back to previous versions
 - Collaboration
     - Helping with merge conflicts
     - Simultaneous development
 - Develop and test new stuff (on `branches`) without breaking the production (on the `master`/`main`/`trunk` branch)

### How to install git?

- `brew` or `apt` on Mac, Linux
- https://gitforwindows.org with the `git bash` programme (my recommendation)


### GitLab, GitHub?

*Git* is the version control *software*. That's what everyone uses and needs to install. 

GitLab and GitHub are online services built around Git. Nowadays, they provide much more than pure version control
- user management: e.g. user access
- developer / IT time
- issues: discussions about bugs, improvement ideas, ...
- pull requests (= merge request on GitLab): add  a new contribution to the main branch and discuss why this contribution is important and correct

GitHub has been bought by Windows a while ago.

GitLab is an "open-core" company. gitlab.com is very much like GitHub. An "open-core" is entierly open source, but have paid programs on top (unlike GitHub which hides their own code).

git.uibk.ac.at is a **local gitlab server** and is only good for local university projects. With a local repository at UIBK you know exactly where the data is stored. You can move repositories around, so starting at UIBK and then move to gitlab.com is always an option, because you have a full copy of all the code and changes on your computer. However, moving the repository will not include all the online extra info, e.g. **issues** with discussions, history of **pull requests** with discussions, statistics, ...

### Examples of utilization of GitLab/GitHub

**Project management:**
- https://github.com/GLIMS-RGI/rgi7_scripts/issues

**Website:**
- https://github.com/OGGM/oggm.github.io (static webpage generator inside (e.g. jekyll, pelikan)
- https://github.com/OGGM/tutorials (`jupyterbook` makes webpages from jupyter notebooks)
- https://github.com/OGGM/oggm-edu (made with https://readthedocs.org : open-source project documentation)
- https://git.uibk.ac.at/acinn/stations-metadata

More on github pages:
- Github *builds* and *hosts* the *static* website, which does not need more computing resources
- GitHub Pages can be used to programm/maintain web pages with git
- static websites don't require any background calculations on the server (only on your own browser), dynamic websites do
- github actions: every time a commit is added, github is doing something (e.g. build the website, test the code) 

**Publication:**
- Works only nicely with Latex or text based editors
- Overleaf / HackMD <-> GitHub sync 

**Code:**
- https://github.com/OGGM/oggm
- all of GitLab / GitHub

**DOI: git with zenodo**
- [linking github with Zenodo for permanent citable code](https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content)

### Not so nice with git

- Pictures, data, binary files:
    - if you change a picture, netCDF file, `git` can not understand the actual differences between the versions
- Branches and collaborative is quite a learning curve (worth it though)
- people working on the same script might result in conflicts which are sometimes complicated to solve (note that this is the very nature of code change conflicts - in fact git is actually trying to help us here)
- git GUIs are confusing (I recommend to learn with the command line first)
- sometimes issues with cloud data storage (e.g., pClouddrive) for commits
- First collaboration among people can become chaotic (learning curve)
- if you do something slightly different than your "normal" workflow, you might get "errors" or "warnings", so you might feel "afraid" that you do something wrong when "forcing" something ... 

### Not so nice with gitLab @UIBK

- slightly more complex if people outside of the university want to join

### Not so nice with github

- Physical Location of data is not known, closed source company
- Gitlab in turn is "open core" company, which is nice

## Learning git

Some resources:
- https://git-scm.com/book/en/v2 
- https://lab.github.com 
- https://about.gitlab.com/learn

### Getting started with git

- you always want a local + online version of git
- when created, run `git clone https://...` in the terminal with the "clone with HTTPS" path
- if you do not want that you have to write the password every time, use SSH, but need to exchange "keys" for each machine where you use it:
    -  [Gitlab ssh](https://docs.gitlab.com/ee/ssh)
    -  [Github ssh](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

**"holy trinity" of git**: `git fetch` (from online repo), `git status` will show status and possible changes, then `git merge` (or `git pull`, which is the combination of `fetch` and `merge`).
- `git commit -a -m` (-a also commits unstaged files)
- `git status` tells you what changed 
- track new files in repository with `git add` + filename

**The four commands which require internet access:**
- `git clone`, `git fetch`, `git pull` (`git fetch` + `git merge`), `git push`

### Collaborating with `git`

**Branches in git are the basis for collaboration.**
- Upstream repo (main Repo, the "holy" one the one you don't want or can push to)
- Fork (named "origin") to clone from, i.e. Local Repo (where you add your changes ideally in a dev branch)
- Push changes to origin (fork), from that create pull request to Holy Repo

**Update your local repository after merge**
- configure "upstream" to point to the holy repo


**What happens when there are changes at the Holy Repo while you are working on dev?**
- most of the time you can ignore. But if you need the updates follow the recommendation below.
- commit your changes on local dev
- git fetch upstream (from Main aka Holy Repo), git pull on clean master branch (not on dev branch)
- Best option is git rebase from dev to local master (avoid git merge)
- If conflicts arise you have to solve them (online or locally)


### `git` cheatsheet

If you forget stuff you can come here to get a quick recap. These things should also be easy to google ;)

- `add`
- `commit`
- `branch`
    - 	`master` (or `main` or `trunk`) - the production version of the code. `Master` is the traditional name, but `main` or `trunk` is used to avoid slave/master associations. There are no actual differences.
- `push`
- `fetch` - get the status of the online repository
- `pull` = `fetch`+ `merge`
- **Merge request** or **pull request** - changes to the code on a development branch. Used to signalize that you have useful changes which may or may not be ready for production. **Pull requests** can contain multiple commits and you can add more commits after opening the request. **Pull requests** must be approved/resolved before they are merged into the `master branch`.
- **Issues** - purely discussions

## git repository from scratch

Initiate the repo in the folder of choice with `git init` to create a `.git` folder. Any folder with a `.git` folder in it is a git repository. Now all git commands can be used inside the folder.

`git status` shows all tracked (green) and untraked (red) files and the current branch. Files can be ignored in a `.gitignore` file but generally we don't want untracked files, so either they should be staged by `git add filename` and commited `git commit -a -m "meaningful message"` or ignored in the `.gitignore` file. 

## Branches

In fact, everything in Git is a Branch.

Branches become important when working collaboratively on a project, however, they can usually be avoided on personal projects with no collaborators.
Although branches can be used to keep the "development" version of the code from a "clean/working" state, this can be achieved without having multiple branches. A better way to achieve the same result is to **use tags** to mark the clean versions of the code.

Whenever possible, avoid solving merge conflicts in the main branch;  use development branches instead.

A good way of not getting into this situation in the first place is to get in the habit of always fetching and merging changes before you start working on a project: this way you will always work on the most up-to-date copy.

With checkout origin/main -> you are changing in the branch origin/main. 

In the local git repository you can find a `.git` folder (hidden folder) where all the changes are stored.


## Workflow for collaboration

If you want to contribute to an existing project, **DO NOT** clone the "Holy repo". Instead:
1. **Fork** the repository. This will create a full copy under your own namespace. Note that this step might take a while: this is because the full repository is copied. This fork becomes your origin by cloning it.
2. **Clone** the fork that you have just created. You can check the origin with `git remote -v` (here `v` is equivalent to `--verbose`)
3. Make a new **branch**, e.g. "dev" (`git branch -b dev`). Do all your work on this new branch: your local `main` branch should stay untouched (as well as `origin/main`). (*TODO: Anyone wants to explain why/how exactly this makes our lives easier?*)
4. As with personal projects, you **commit** all changes that you want to keep.
5. To **push** commited changes to the origin (not the `main` branch though, we're still talking about the `dev` branch!): `git push origin dev`
   If you now check online, you should see that there are multiple branches in your project.
6. Once you're happy with your changes to the project and you want them to be merged into the project: you submit a **pull/merge request**. Specifically, you want the `dev` branch of your fork to be merged into the `main` branch of the project. Based on the settings, you will usually get an email once your changes are accepted.
    - In a pull request: use an informative title
    - Etiquette: it's polite to thank for contributions, but no need for greetings or other extra pleasantries
    - If you make a mistake and don't want your changes to be merged after all, it's good practice to close your own merge request (it can't be deleted).
    - NOTE: as a maintainer of the "Holy repo", you are responsible for reviewing the merge requests. When doing this, you want to *squash* the commits (if there's       more than one) from other contributors. This keeps the history of the main branch in the Holy repo cleaner.
      However, even as a maintainer, if you collaborate with other people on a project, you do NOT want to push directly to the Holy repo. Even then you want to do       that via merge/pull requests.
7. If we want to update the local repository to reflect the changes in the Holy repo (example with the ACINN repo): `git remote add upstream git@git.uibk.ac.at/acinn/icu/AdvPro_SS22.git`. "Upstream" here is the address of the Holy repo, from which we will be able to fetch the changes, whereas "origin" is still our fork. To check all our remotes, do `git remote -v`.
8. Then, to fetch the changes from the Holy repo: `git fetch upstream`. To merge these into the main branch: `git checkout main` and then `git merge upstream/main`. 
9. To continue working on the project, the best way is to make a new branch again. I.e. once our `dev` branch is merged into the Holy repo, this branch is "dead" to us, and we want a new branch for the next merge request. 
    - **Recommended:** One option is to always start a new branch. In the end you could end up with hundreds of branches, but you can always delete those at a later stage when you're sure that you don't need them anymore. 
    - **Not recommended:** The second option is to overwrite the `dev` branch (do this only with *A LOT OF CAUTION* since your changes on this branch which are not merged yet would be lost forever - google how to do this yourself if you're certain that this is what you want to do).

