# react-notes
Notes on everything we're learning about React and creating a React app


npx create-react-app <name-of-folder> // Doesn't take capitalized letters, and npx allows you to install something without installing it/downloading it locally.

We create components that we export. Each component returns something that is contained within one parent set of tags. 

Within our App.js, we can pass through poperties such as this.props within a component.

Constructors are something that are added to classes. Constructo method allows us to run new instances of a class 

this.state is designed to change/react to user process and flow thru application, which is why we set it in constructor



npm i react-router-dom to install react router
npx create-react-app . to create a react app in a folder that already exists

To create a new github branch, 
`git checkout -b [nameOfBranch]`
In bottom left of VSCode, you can see which branch you're on as well as the names of your other branches.


[Group git notes](https://hackmd.io/8eIt6vTgS5q3ZJakZy9SpQ?view):

https://hackmd.io/8eIt6vTgS5q3ZJakZy9SpQ?view

HOW TO GROUP GIT: 

- Local repo = On your computer

- Remote repo = Github.com repo

- Origin = Your forked and cloned remote repo

- Upstream = The source of your remote repo, i.e. the manager's repo

After forking and creating a `git clone [forked URL]` on your computer...
1. `git remote add upstream [upstream URL]`
2. `git remote -v` *To ensure you have an origin and a now an upstream link.*
3. `git checkout -b [mybranchname]` 
4. \* Work on your project *
5. Push changes to your remote repo: `git add .`, `git commit -m "Commit message"`, `git push`
6. Go to github.com and submit a pull request from your development branch to the manager's main branch
7. Manager accepts request

*Then, manager merges a pull request:*

8. `git checkout main`
9. `git pull upstream main` (Manager uses `git pull origin main`)
10. `git push origin main` (Manager doesn't need to do this step)
11. `git checkout [mybranchname]`
12. `git merge main`
13. `git push`


[How to add commit messages when merging branches](https://gist.github.com/kenandersen/2042103942473af82dd2):


// You'll see this message if you git commit without a message (-m)

// You can get out of it with two steps:

// 1.a. Type a multi-line message to move foward with the commit.

// 1.b. Leave blank to abort the commit.

// 2. Hit "esc" then type ":wq" and hit enter to save your choice. Viola!