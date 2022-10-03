
https://hackmd.io/8eIt6vTgS5q3ZJakZy9SpQ?view

HOW TO GROUP GIT: 

- Local repo = On your computer

- Remote repo = Github.com repo

- [Remote] Origin = Where you 'git clone'd your repo from.

Assuming that everyone has been invited to collaborate on the project so they have push permissions, after you `git clone [URL]` on your computer, do the below in your terminal...
1. `git checkout -b [mybranchname]` to create a local development branch to work on.
2. \* Work on your project *
3. Push changes to your remote repo's development branch: `git add .` (or `git add -A` to add everything in current file and below), `git commit -m "Commit message"`, `git push origin [mybranchname]`
4. Go to the remote repo on github.com and submit a pull request from your development branch to the main branch
5. Resolve any merge conflicts and let your teammates know when you've merged a pull request.

*Then, everyone (including the person who just merged their PR) on the team pulls from the updated <main> branch to update their local <main> branch.*

6. `git checkout <main>`
7. `git pull origin <main>`
8. `git add .`, `git commit -m`
9. `git checkout [mybranchname]`
10. `git merge <main>`
11. `git add .`, `git commit -m`

Reminder: You are NEVER coding or making direct edits to ANY main branch. The only way to modify the main branch is through pull requests and merge conflict resolutions when merging pull requests.

[How to add commit messages when merging branches](https://gist.github.com/kenandersen/2042103942473af82dd2):


// You'll see this message if you git commit without a message (-m)

// You can get out of it with two steps:

// 1.a. Type a multi-line message to move foward with the commit.

// 1.b. Leave blank to abort the commit.

// 2. Hit "esc" then type ":wq" and hit enter to save your choice. Viola!


### How to undo local changes to revert to your most recent commit:
`git reset --hard`
https://docs.gitlab.com/ee/topics/git/numerous_undo_possibilities_in_git/#undo-local-changes

Github notes from Dave: 
http://sethrobertson.github.io/GitFixUm/fixup.html

  
 ### Setting GitHub upstream
 `git config --global push.default current`
[Source]([url](https://stackoverflow.com/a/70015830))
