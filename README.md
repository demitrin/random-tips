## General Tips

Some useful tips for collaborating on a python project with git.

General collaboration tips:
- writing some unit tests can help catch bugs before submitting to the simulator
- using a formatter or linter can make code formatting never an issue (https://github.com/psf/black)
- doing code reviews (via github pull requests) can make code collaboration a lot easier
- using python type annotations (https://docs.python.org/3/library/typing.html) and mypy (https://github.com/python/mypy) can reduce bugs that come from unexpected data types. This suprisingly happens more than we expect

## Git Overview

At a high level, git allows you to work on a project while creating "commit"s, or in plain english, checkpoints. Teams use git so that people on work on the same codebase (files and directories) concurrently. Think google docs but not real-time.

Assuming you know basic git knowledge like `git pull`, `git commit -m '<message>'`, and `git push origin main`, here's some other tips.

- Commit early and often. This is the main "checkpoint" mechanism when coding. Doing a lot of commits has no downsides, but not committing enough could bite you if you ended up writing code that you now need to undo.
- Lots of teams use pull-requests and code reviews rather than pushing directly to the "main" branch. This lets you show your teammates a draft of your code before you submit it to the project. Whenever you start working in a professional environment, this will likely be the workflow
- Try and make use of pre-commit (https://pre-commit.com/) to make some work automated. A really useful thing would be to use a formatter so all code in your project is always formatted (https://github.com/psf/black#version-control-integration).

## Git branches
A git branch is a copy of the code you're working on that is edited separately of other branches. All projects have a "main" branch, but most people work on branches other than "master" while coding.

To create a branch, `git checkout -b <branch_name>`.

This will create a new branch that is a copy of the original branch you were on when creating. A common workflow would be:

```
git checkout main
git pull origin main
git checkout -b <branch_name>
```

From here, all code you change is isolated only to your new branch. You can see the branch you're currently on with `git branch`.

Once you're done making commits on a branch, you can open a pull request with `git push origin <branch_name>`. Then go to your github repository and you should see a pop-up to suggest creating a pull request.

Other git commands I often use:
- `git diff`
- `git status`
- `git checkout <commit_hash>` (checkout a commit)
- `git stash` and `git stash pop`
- `git revert --soft HEAD~1` (undo the latest commit but keep the code changes)
- `git cherry-pick` (https://git-scm.com/docs/git-cherry-pick)
