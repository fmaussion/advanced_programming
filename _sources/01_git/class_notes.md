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
