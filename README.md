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


Group git process from Dave Stach, where origin is your forked repo and upstream is the original repo: 

1. git checkout -b mybranchname // to create and checkout to dev branch
2. *work on your project *
3. commit changes
4. git push origin mybranchname
5. git checkout main
6. git merge mybranchname
7. git push origin main
8. go on github and submit a pull request
9. *git person approves request *
10. git pull upstream main (to update your local)
11. git push origin main (to update your remote if there were changes done by other group members)


[How to add commit messages when merging branches](https://gist.github.com/kenandersen/2042103942473af82dd2):


//You'll see this message if you git commit without a message (-m)
// You can get out of it with two steps:
// 1.a. Type a multi-line message to move foward with the commit.
// 1.b. Leave blank to abort the commit.
// 2. Hit "esc" then type ":wq" and hit enter to save your choice. Viola!