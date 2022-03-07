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

