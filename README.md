<div>    
  <img alt="how to create your own api - this is a guide on how to make your own api using JS, node.js and Heroku! Dont forget to star this repository" src="https://user-images.githubusercontent.com/95686401/177621091-81b2355f-eff5-467d-a81b-3bdec466baba.png" /> 
</div>


## how to create your own API: 
This repository was created as a free, open-source guide on how to create your own API and hosting it. When working on a personal project, it can be quite helpful, and you can even post it on gitHub so that others in the community can utilize it. Feel inspired? Star this repository, so you can always come back and use it!


<div>    
  <img alt="languages" width="250px" src="https://user-images.githubusercontent.com/95686401/177618703-b3400ec7-50ed-4b4e-941d-147437af7ab2.png" /> 
</div>

### clique [aqui](https://github.com/calvitoria/how-to-mock-API/blob/portuguese-language/README.md) para acessar o material em português 🇧🇷

<hr/>

<div>    
  <img alt="before starting, initial configuration" width="350px" src="https://user-images.githubusercontent.com/95686401/177658129-530cf712-dabe-4b4f-af06-03a9063f529f.png" /> 
</div>

1. create the directory you want to have your files. 
> I encourage you to make a github repo and then cloning it, so you can deploy in Heroku using this exact repository.
2. Open your terminal and install npm: ```npm install```
3. type ```code .``` in your terminal to open VScode.
4. Install Express: ```npm install express```
5. you should now have a node_modules folder, a package.json and a package-lock.json file.

<hr/>
<div>    
  <img alt="1. create your database" width="350px" src="https://user-images.githubusercontent.com/95686401/177658177-616660e3-7106-4ba6-bcc0-0cfa1f18cb25.png" /> 
</div>

#### let's start with our databasa file:
1. in the folder of your choice, create a database.json file
> in this example, I created an src folder and a characters folder inside it, with the database.js inside that folder.
(path: src/characters/characters.json)
2. it is important to have in mind the 'template' you will be using in this database.
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
  <img alt="create your index.js file" width="350px" src="https://user-images.githubusercontent.com/95686401/177658207-901e3cd6-85b1-43a7-878f-7ec338ab4520.png" /> 
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
  <img alt="edit your package.json" width="350px" src="https://user-images.githubusercontent.com/95686401/177658247-5f6220ca-03d8-4bd3-b12f-9e45a44763d3.png" /> 
</div>

#### now let's edit our package.json
1. in your package.json file, add the object "scripts" with the key "start" and value "node index.js"

```
"scripts": {
  "start": "node index.js"
},

```

your package.json file should be looking similar to this: 

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
  <img alt="deploy your database" width="350px" src="https://user-images.githubusercontent.com/95686401/177658275-c0a1a02f-c92f-4a2c-99d7-3b30529eb4c0.png" /> 
</div>

#### ok, now we need to deploy our API
1. create an account or login at [heroku](https://www.heroku.com/home)
2. at heroku website, create a *new app*. Name it after your API .
3. after clicking on 'create app' you will be redirected to a new page, where you can choose how you will be deploying your API.
> I used the github method. Just login, choose the repository you will be connecting and choose the way you want to deploy.
4. use the button 'open app' to see the magic! Depending on how you made your files, you might have to type the endpoint of your database as well.

> if you build your application just like the way I did, just clicking the button wont be enough! You will need to type in the URL the endpoint of your json.

<hr/>

<div>    
  <img alt="using your api" width="350px" src="https://user-images.githubusercontent.com/95686401/177618276-e053e9cf-dad0-4e4d-b556-2f9bbeb4c8bf.png" /> 
</div>

#### Using your API: 
You can use the database by sending GET, POST, PUT, DELETE... requests to it.

```
fetch('https://NAME-OF-YOUR-API.herokuapp.com/DATABASE') 
  .then(response => response.json())
  .then(data => console.log(data));
```
 
simple as that! 


<div>    
  <img alt="want to help the community? translate this content to your mother language!" src="https://user-images.githubusercontent.com/95686401/177618708-93d1f965-6d91-469e-995d-407e89be1483.png" /> 
</div>

If you got interested in contribuiting to this project, you can just clone the repository, open a new branch like ```"________-language"```, then just follow this README structure. If you want to add the Heading immages you can make a copy of [this](https://www.canva.com/design/DAFFwQQCaxw/8xlYGBJfRGUvEMcrQ1bn-g/edit?utm_content=DA[…]m_campaign=designshare&utm_medium=link2&utm_source=sharebutton) 
template at Canva and edit. If you don't feel like it, no worries! Just make a normal heading to each step! If you want to use the canva template, you can use github issues to transform the png file to a URL. 

<hr/>

> I also post educational content on my [linkedIn](https://www.linkedin.com/in/calvitoria/), check it out!
> this is a step by step of how to create your mock api. The content you see here is inspired by [this](https://www.youtube.com/watch?v=AC62XYv7Yos) youtube video from Stack Mobile.
