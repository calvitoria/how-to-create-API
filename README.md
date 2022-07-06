<div>    
  <img alt="how to create your own api - this is a guide on how to make your own api using JS, node.js and Heroku! Dont forget to star this repository" src="https://user-images.githubusercontent.com/95686401/177621091-81b2355f-eff5-467d-a81b-3bdec466baba.png" /> 
</div>


## how to mock an API
This repository was created as a free, open-source guide on how to create your own mock API. When working on a personal project, it can be quite helpful, and you can even post it on gitHub so that others in the community can utilise it. Feel inspired? Atar this repository, so you can always come back and use it!


<div>    
  <img alt="languages" width="250px" src="https://user-images.githubusercontent.com/95686401/177618703-b3400ec7-50ed-4b4e-941d-147437af7ab2.png" /> 
</div>

### clique aqui para acessar o material em português 🇧🇷

<hr/>

<div>    
  <img alt="before starting" width="350px" src="https://user-images.githubusercontent.com/95686401/177616577-6c5eb48f-c6dd-4f0f-9f2e-ddda855b72d5.png" /> 
</div>

#### initial configuration: 
1. create the directory you want to have your files. 
> I encourage you to make a github repo and then cloning it, so you can deploy in Heroku using this exact repository.
2. Open your terminal and install npm: ```npm install```
3. type ```code .``` in your terminal to open VScode.
4. Install Express: ```npm install express```
5. you should now have a node modules folder, a package.json and a package-lock.json file.

<hr/>
<div>    
  <img alt="1. create your database" width="350px" src="https://user-images.githubusercontent.com/95686401/177616577-6c5eb48f-c6dd-4f0f-9f2e-ddda855b72d5.png" /> 
</div>

#### let's start with our databasa file:
1. in the folder of your choice, create an database.json file
> for this exemple I created a src folder and a characters folder in it, with the database.js populating it. (src/characters/characters.json)
2. it is inportant to have in mind the 'template' you will be using in this database.
exemple: a chraracter API 

```
[
    {
      "id": 0,
      "name": "characters name",
      "series": "the series this character is from",
      "thumbnail": "image url",
      "description": "description of the character",
    }
  ]
```

> You can modify this example to fit your needs

<hr/>

<div>    
  <img alt="create your index.js file" width="350px" src="https://user-images.githubusercontent.com/95686401/177616577-6c5eb48f-c6dd-4f0f-9f2e-ddda855b72d5.png" /> 
</div>

1. create a index.js file
2. in your index.js file, type the following code: 

```const express = require("express")
const app = express();
const port = process.env.PORT || 3000

const quiz = require("./src/characters/characters.json") // path of your database json file
app.get("/characters", (req, res) => {
    return res.json(characters)
})

app.listen(port, () => {
    console.log('server is running...')
})
```
> to check if it's all good and running, type in your terminal ```node index.js``` the console.log should be printed.
> pay attention to the path of your files!

3. create a .gitignore file and add node_modules to it. ! this is really important ! to make a deploy to Heroku, you should NOT upload node_modules with the rest of your files.

<div>    
  <img alt="2. create your server" width="350px" src="https://user-images.githubusercontent.com/95686401/177617318-f2998246-f642-4910-aca8-2a0ffa9fb60b.png" /> 
</div>

#### now let's edit our package.json
1. in your package.json file, add the object "scripts" with the key "start" and value "node index.js"

```
"scripts": {
  "start": "node index.js"
},```

your package.json file should be something like this: 

```
{ 
  "scripts": {
  "start": "node index.js"
},
  "dependencies": {
    "express": "^4.18.1"  // remember the 'npm install express' we just did? ;)
  }
}

```
<hr/>

<div>    
  <img alt="3. deploy your database" width="350px" src="https://user-images.githubusercontent.com/95686401/177617693-78ffa223-51cd-4dcb-8ca0-e0ebc5c8308f.png" /> 
</div>

#### ok, now we need to deploy our API
1. create an account or login at [heroku](https://www.heroku.com/home)
2. at heroku website, create a *new app*. Name it after your API .
3. after clicking in 'create app' you will be relocated to a new page, where you can choose the way you will be deploying your API.
> I used the github method. Just login, choose the repository you will be connecting and choose the way you want to deploy.
4. use the button 'open app' to see the magic! Depending on how you made your files, you might have to type the endpoint of your database as well.

> if you make it just like the exemple I give, just clicking the button wont be enough! You will need to type in the URL the endpoint of your json.

<hr/>

<div>    
  <img alt="using your api" width="350px" src="https://user-images.githubusercontent.com/95686401/177618276-e053e9cf-dad0-4e4d-b556-2f9bbeb4c8bf.png" /> 
</div>

#### Using your API: 
You can use the database using GET, POST, PUT, DELETE... requests to it. 

```
fetch('https://NAME-OF-YOUR-API.herokuapp.com/DATABASE') 
  .then(response => response.json())
  .then(data => console.log(data));
```
 
simple as that! 


<div>    
  <img alt="want to help the community? translate this content to your mother language!" src="https://user-images.githubusercontent.com/95686401/177618708-93d1f965-6d91-469e-995d-407e89be1483.png" /> 
</div>

<hr/>

> this is a step by step of how to create your mock api. The content you see here is inspired by [this](https://www.youtube.com/watch?v=AC62XYv7Yos) youtube video from Stack Mobile.
