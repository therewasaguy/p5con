# Contributing to p5.js
This repo will help us get started contributing to p5 at the p5 contributor's conference!

# Attendees
- Jason Sigal @[therewasaguy](http://github.com/therewasaguy)

# T.O.C.
1. Open Source
  - Brief History of Open Source
  - [Open Source Licenses](http://choosealicense.com/licenses/)
  - [Examples of Successful Open Source Projects](http://en.wikipedia.org/wiki/List_of_free_and_open-source_software_packages)
  - General & Project-Specific Guidelines
    - Style: [idiomatic.js](https://github.com/rwaldron/idiomatic.js/)
    - Example guidelines from [three.js](https://github.com/mrdoob/three.js/blob/master/CONTRIBUTING.md), [bower](https://github.com/bower/bower/blob/master/CONTRIBUTING.md)


2. Ways to Contribute
  - Discussion --> [Issues](https://github.com/processing/p5.js/issues)
    - Bug reports
    - Feature Requests
  - Code --> [Pull Requests](https://github.com/processing/p5.js/pulls)
    - Bug Fix
    - New Feature
    - Documentation
    - Example
    - Tests

3. Set up --> [p5 Development Wiki](https://github.com/processing/p5.js/wiki/Development)

  0. Install System Tools:
    - [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
    - [node.js](nodejs.org) (includes npm, the Node Package Manager)
    - Grunt CLI: ``npm install -g grunt-cli``
  1. Fork, Clone, Configure Remotes, Install Dependencies
    - Fork https://github.com/processing/p5.js to your github account.
    - Clone your fork of the repo from Terminal: ``git clone https://github.com/<your-username>/p5.js``
    - Navigate to the newly cloned directory: ``cd p5.js``
    - Add a reference to the original repo as a remote called "upstream":
        ``git remote add upstream https://github.com/processing/p5.js``
    - Install Dependencies: ``npm install``  --> This creates a folder called "node_modules" with all the dependencies listed in "package.json"
  2. Get Latest Changes
    - If you cloned a while ago, get the latest changes from upstream:
      - ``git checkout master`` --> switch to your "master" branch
      - ``git pull upstream master`` --> pull changes from the "master" branch of the remote repo we called "upstream"
  3. Create a new branch (optional)
    - ``git checkout -b <topic-branch-name>``
      -  ``-b`` creates the branch
      - ``checkout`` makes this your current branch. Updates all the files to reflect whatever’s in that branch
      - ``checkout -b`` does both at the same time.
      - *This is a good idea in case your PR is not accepted right away, and you want to work on something else in the meantime. Because any commits you make to a branch with an unresolved pull requests will be added to the pull request.*
  4. Make Some Edits...
    - p5.js and p5.min.js are built from the modules in the /src folder. Edit your module(s)
    - ``grunt`` --> builds new version of the library. Also runs a bunch of other tasks defined in Gruntfile.js, including jshint which enforces [these style guidelines](https://github.com/processing/p5.js/blob/master/src/.jshintrc).
    - ``grunt watch`` --> every time you save, grunt re-builds the library
    - *Recommended: create an example in the /examples folder to manually test whatever you're working on if it is a bug fix or new feature. You may consider adding this as an example, or leave it out when you commit changes.*
  5. Write Automated Tests (optional)
    - Tests live in "test/unit/<unit_name>" and are linked via "[test/test.html](https://github.com/processing/p5.js/blob/master/test/test.html)" 
    - [More info on Testing with p5.js](https://github.com/processing/p5.js/wiki/Development#testing)
  6. Document Changes (optional)
    - Documentation is generated automatically from inline comments when you run ``grunt`` or ``grunt yui``
    - [p5.js Inline Documentation guide](https://github.com/processing/p5.js/wiki/Inline-documentation)
    - example: ellipse() [src](https://github.com/processing/p5.js/blob/master/src/shape/2d_primitives.js#L112) / [doc](http://p5js.org/reference/#/p5/ellipse)
    - To view your changes, clone the [p5.js-website repo](https://github.com/processing/p5.js-website) and replace the [reference/data.json](https://github.com/processing/p5.js-website/blob/master/reference/data.json) file with the new file from your p5.js repo. ***Note: The p5.js website needs a PHP server in order to run.

Addendum:
- Resolving Merge Conflicts
