# Assignments

## git exercise 1: a typical workflow for a 1 person project

"due date": 21.03.2022

0. Don't forget to setup git as explained here: https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup

1. Create an account on one of:
    - https://github.com
    - https://gitlab.com
    - https://git.uibk.ac.at

    Take your decision on the platform based on what you want the account for, and the topics we have discussed 
    in class. If you are not sure, simply use git.uibk.ac.at (this is what we will use for exercise 2 anyways).

2. Create a new repository of your choice *online*. Name it what you want (test something)

3. Clone it locally on your laptop

4. Add one file or two, add some content to the files. Commit them.

5. Changes the files a bit more, commit again.

6. Now push the changes to your online repository.

7. Online now, edit one of the files with the online editor. Commit the changes online.

8. Pull the changes locally, so that the changes that happened online are now available locally.

That's it! You've already learned a bunch about git with only just this workflow!


## git exercise 2: a typical workflow for a team project

"due date": 28.03.2022

We will learn how to do a "merge request" in class. Your tasks this week are to:

1. set-up `git` to work without a password (I recommend SSH but find the documentation that works for you).
2. open a second merge-request to https://git.uibk.ac.at/acinn/icu/AdvPro_SS22, this time adding some information to your home page: a photo of your choosing (a pet, a mountain, your bike, whatever you like), link it into your bio and add a short description of it. 
3. I will review it during the week and you will have a little more to do ;-)

## Exercise 3: build the documentation of a software project

"due date": 28.03.2022

This task is loosely git related, and it is meant to teach you to do something new and get ready for one of your "graded assignments": contributing to an open-source project.

Pick a project you like (xarray, metpy, something else) which has a [sphinx](https://www.sphinx-doc.org) based documentation (that's almost all of them) and **follow the project's instructions to build the documentation locally**. xarray's documentation takes a bit to build but the process is well documented. Get acquainted with sphinx by playing around a bit.

**OR**

Build the [oggm-edu](https://edu.oggm.org) website locally (also built with sphinx but a bit simpler than xarray's) and let me know if I need to work on [documenting](https://github.com/OGGM/oggm-edu/blob/master/BUILD_HOWTO.rst) this better.

**OR**

(advanced) Build a documentation of your own project from scratch using sphinx. I'll help.
