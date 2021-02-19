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
5. Push changes to your remote repo: `git add .` (or `git add -A to add everything in current file and below`), `git commit -m "Commit message"`, `git push`
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

# Using Axios in React.
```javascript
useEffect( () => {
    fetch('http://acnhapi.com/v1/villagers')
    .then(response => response.json())
    .then(rData => {
      rData = Object.values(rData) // Converts object of objects to array of objects.
      // console.log(rData) // responseData
      // console.log(rData[0].name['name-USen']) // responseData
      // let characterNames = rData.map( (char, i) => {
      //   return char.name['name-USen']
      // })
      setCharacters(rData)
    })
  }, [])
```


brew services start mongodb-community@4.4
mongo (to enter shell)
quit() (to quit shell)

brew services stop mongodb-community@4.4

brew services start postgresql 

brew services list (to see what's active)


MONGODB

show dbs // Show databases

use users // Either switches to a database named 'users' or creates a new db named 'users'

show collections // Show collections

db.people.insert({ // Create a new collection called people.
    ... name: 'Fred', // mongo shell provides us with ... to indicate that we're continuing.
    age: 21
})

db.people.find() // Returns all documents (what we called 'rows' in Sequelize) in people collection

db.people.find({name: "Kenny"}) // To find a specific page

### Conditional queries: 
db.people.find({age: {$gte: 21}}) // Greater than or equal to
db.people.find({age: {$lte: 35}}) // Less than or equal to


db.people.find({age: {$gte: 45, $lte: 47}}).sort({name: 1}) // 1 sorts ascending, -1 sorts descending.

db.people.update({name: "Adrian"}, {$set: {age: 77}}) // Modifies one page (the first one) where the name = "Adrian"; set age to 77.


// Update is only for updating pre-existing fields. Add is used for adding new fields.

db.people.update( {name: {$lt: "M"}}, {$inc: {age: 10}}, {multi: true}) // Find people whose names beging with a letter before M, increase their age by 10, and do this for every result you find, not just the first search result.

db.people.find().pretty()

db.people.update( { name: {$lt: "M"} }, { $mul: {age: 2} }, {multi: true} ) // If their name starts with a letter before M, multiply their age by 2, and do it for all results found and not must the first one.

db.people.update( { age: {$gt: 55}}, { $set: {age: "old" } } , {multi: true})

db.people.remove( { name: "Emma" } ) // Deletes/removes Emma. No need to use "multi"

ODM = Object Document Mapper (instead of ORM, since Mongo isn't a relational database)




//// Using Mongoose in Express
unit 3 > labs and codealongs > family-tree
mkdir
To create an Express app, npm init -y
then npm i express
touch index.js
npm i mongoose 

Inside index.js,
const express = require('express')
const app = express()
app.get('/', (req, res) => {
    res.send('It is working') // sanity check
})

app.listen(3000, () => console.log("Listening on Port 3k"))

then in terminal: nodemon

Make sure console.logs are working and that brew services start mongodb-community@4.4



How to view your database and models in mongo:

Terminal: 
mongo
show dbs
use familyTree
show collections



cors = cross origin resource sharing, so that you can API fom other places such as a react app

How to update mongoose version to not have terminal error messages:
https://stackoverflow.com/questions/66185671/warning-accessing-non-existent-property-mongoerror-of-module-exports-inside-c

`npm install mongoose@5.11.15`

Authentication, simply another way to do this, not necessarily tied to what we're doing now
JWT = JSON web token, instead of sessions. Still uses secret, uses a complex algorithm to both hash and encrypt to return a string that includes information on when it should expire, etc.

Something about a signature

Server generates a token that it sends to the client, client has to always send that token to the server whenever sending info 

(Btw, JWT token is redundant--JSON web token token, similar to how CSS stylesheets is also redundant)


Token only relies on secret

///// Passport, JWT tokens, MERN auth apps
We'll use passport, but remember how we had the Local Strategy thing we used in Passport? This time we'll use a JWT strategy which will take the place of sessions.

- Will create an environment variable to store our secret, where the secret will be a string value
- Every time our app generates a token (by hashing and encrypting user data with our secret), it spits out a token that includes a 'signature,' which is the part of the token that has the secret in it encrypted

To reiterate: Signature is the encrypted secret part of a token (third part), other part includes encoded header and encoded payload data (actual user data)

