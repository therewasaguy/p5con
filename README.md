# Contributing to p5.js
This repo will help us get started contributing to p5 at the p5 contributor's conference!

# Attendees
- Jason Sigal @[therewasaguy](http://github.com/therewasaguy)

# T.O.C.
## Open Source
  - Brief History of Open Source
  - [Open Source Licenses](http://choosealicense.com/licenses/)
  - [Examples of Successful Open Source Projects](http://en.wikipedia.org/wiki/List_of_free_and_open-source_software_packages)
  - General & Project-Specific Guidelines
    - Style: [idiomatic.js](https://github.com/rwaldron/idiomatic.js/)
    - Example guidelines from [three.js](https://github.com/mrdoob/three.js/blob/master/CONTRIBUTING.md), [bower](https://github.com/bower/bower/blob/master/CONTRIBUTING.md)


## Ways to Contribute
  - Discussion --> [Issues](https://github.com/processing/p5.js/issues)
    - Bug reports
    - Feature Requests
  - Code --> [Pull Requests](https://github.com/processing/p5.js/pulls)
    - Bug Fix
    - New Feature
    - Documentation
    - Example
    - Tests

## Set up --> [p5 Development Wiki](https://github.com/processing/p5.js/wiki/Development)

  0. **Install System Tools:**
    - [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
    - [node.js](nodejs.org) (includes npm, the Node Package Manager)
    - Grunt CLI: ``npm install -g grunt-cli``
  1. **Fork, Clone, Configure Remotes, Install Dependencies**
    - Fork https://github.com/processing/p5.js to your github account.
    - Clone your fork of the repo from Terminal: ``git clone https://github.com/<your-username>/p5.js``
    - Navigate to the newly cloned directory: ``cd p5.js``
    - Add a reference to the original repo as a remote called "upstream":
        ``git remote add upstream https://github.com/processing/p5.js``
    - Install Dependencies: ``npm install``  --> This creates a folder called "node_modules" with all the dependencies listed in "package.json"
  2. **Get Latest Changes** ^
    - If you cloned a while ago, get the latest changes from upstream:
      - ``git checkout master`` --> switch to your "master" branch
      - ``git pull upstream master`` --> pull changes from the "master" branch of the remote repo we called "upstream"
  3. **Create a new branch** ^
    - ``git checkout -b <topic-branch-name>``
      -  ``-b`` creates the branch
      - ``checkout`` makes this your current branch. Updates all the files to reflect whatever’s in that branch
      - ``checkout -b`` does both at the same time.
      - *This is a good idea in case your PR is not accepted right away, and you want to work on something else in the meantime. Because any commits you make to a branch with an unresolved pull requests will be added to the pull request.*
  4. **Make Some Edits...**
    - p5.js and p5.min.js are built from the modules in the /src folder. Edit your module(s)
    - ``grunt`` --> builds new version of the library. Also runs a bunch of other tasks defined in Gruntfile.js, including jshint which enforces [these style guidelines](https://github.com/processing/p5.js/blob/master/src/.jshintrc).
    - ``grunt watch`` --> every time you save, grunt re-builds the library
    - *Recommended: create an example in the /examples folder to manually test whatever you're working on if it is a bug fix or new feature. You may consider adding this as an example, or leave it out when you commit changes.*
  5. **Write Automated Tests** ^
    - Tests live in "test/unit/<unit_name>" and are linked via "[test/test.html](https://github.com/processing/p5.js/blob/master/test/test.html)" 
    - [More info on Testing with p5.js](https://github.com/processing/p5.js/wiki/Development#testing)
  6. **Document Changes** ^
    - Documentation is generated automatically from inline comments when you run ``grunt yui``
    - [p5.js Inline Documentation guide](https://github.com/processing/p5.js/wiki/Inline-documentation)
    - [DocBlockr](https://github.com/spadgos/sublime-jsdocs) is a Sublime Text package to help auto-format your inline docs.
    - Example: ellipse() [src](https://github.com/processing/p5.js/blob/master/src/shape/2d_primitives.js#L112) / [doc](http://p5js.org/reference/#/p5/ellipse)
    - To view your changes, clone the [p5.js-website repo](https://github.com/processing/p5.js-website) and replace the [reference/data.json](https://github.com/processing/p5.js-website/blob/master/reference/data.json) file with the new file from your p5.js repo. ***Note: The p5.js website needs a PHP server in order to run.
  7. **Commit Your Changes**
    - ``git add <files you want to include>``
    - ``git commit -m <your short commit message>``
    - Commit messages should explain what change(s) you made in the imperitive tense, i.e. "fix bug with ellipse"
    - If you have a messy commit history, you can use [git rebase](https://help.github.com/articles/about-git-rebase/) to tidy up before sending the pull request.
  8. **Locally Merge (or rebase) Upstream Changes** ^
    -  ``git pull upstream master`` --> merge your changes with upstream changes
    -  Or, ``git pull --rebase upstream master`` --> applies your changes ontop of the upstream changes
  9. **Push To Your Fork**
    - `` git push origin <topic-branch-name>``
  10. **Open Pull Request**
    - [GitHub info on Using Pull Requests](https://help.github.com/articles/using-pull-requests/)
    - Clear description of changes, clear title, imperative tense (i.e. "fix bug")
  11. **Discuss & Amend Pull Request**
    - Pull Requests can be discussed, just like issues [example](https://github.com/processing/p5.js/pull/454)
    - Pull Requests are not static snapshots of your repo. They update whenever you add more commits to the branch, until the PR is accepted.

^ These are optional, but recommended, and sometimes these things (like adding documentation) encompass your entire contribution.

# Useful Git Commands
- ``git remote -v`` List all your remotes "verbosely"
- ``git pull <name_of_the_remote> <branch_name>``
- ``git push <name_of_the_remote> <branch_name>``
- ``git checkout -b <topic-branch-name>`` Create a new branch and check it out
- ``git stash``   Stash all uncommitted changes you’ve made to the branch. You can get them back later.
- ``git log``    Show commit history.
- ``git status``    Show branch and pending changes.
- ``git diff``   View merge conflicts
- ``git grep "something()"`` Search for things in your working directory.
- ``git commit --amend`` Amend your previous commit rather than creating a new commit


# Addendum:
## Resolving Merge Conflicts:
- Conflicts occur when branches have conflicting modifications that cannot be automatically resolved/merged. When you try to merge (i.e. pull upstream changes), if there are conflicts, git tells you and adds this stuff to your file:
```
<<<<<<< HEAD

Here is what you had locally
=======
Here is what was in the thing you tried to merge
>>>>>>> 59685c301d09b58fdac23d616
```
You can fix manually by picking which one you want and getting rid of all this: <<<<<< HEAD ======= >>>>> 583….
