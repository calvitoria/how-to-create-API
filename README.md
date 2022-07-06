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
  <img alt="1. create your database" width="350px" src="https://user-images.githubusercontent.com/95686401/177616577-6c5eb48f-c6dd-4f0f-9f2e-ddda855b72d5.png" /> 
</div>

#### let's start with our databasa file:
1. in the folder of your choice, create an database.json file
2. it is inportant to have in mind the 'template' you will be using in this database.
exemple: a chraracter API 

```
{
'characters': [
    {
      "id": 0,
      "name": "characters name",
      "series": "the series this character is from",
      "thumbnail": "image url",
      "description": "description of the character",
    }
  ]
}
```

> You can modify this example to fit your needs

<hr/>


<div>    
  <img alt="2. create your server" width="350px" src="https://user-images.githubusercontent.com/95686401/177617318-f2998246-f642-4910-aca8-2a0ffa9fb60b.png" /> 
</div>

#### now let's create our server
1. in your terminal, install NPM ``` npm install -g json-server ``` 
>if the response on the terminal says youre blocked: add the npm registry
``` npm install -g json --registry https://registry.npmjs.org ```  
2. then type the command ``` json-server --watch database.json  ``` (the json file you just created) 
3. accsess your database online using the output from your terminal
 > something like https://localhost:3000/YourApiObject


<hr/>


<div>    
  <img alt="3. deploy your database" width="350px" src="https://user-images.githubusercontent.com/95686401/177617693-78ffa223-51cd-4dcb-8ca0-e0ebc5c8308f.png" /> 
</div>

#### ok, now we need to deploy our database
1. create an account or login at heroku
2. deploy the json you created using [heroku](https://www.heroku.com/home)
3. initialize your project: in your terminal type the command ``` npm init ``` 
> just keep pressing enter and then type yes to complete
4. you now have your package.json file
5. now in your terminal type the command ``` npm i ``` 
6. and then ``` npm i json-server --registry https://registry.npmjs.org``` 
7. now your package.json will have a key 'dependencies' with json-server in it and its version.
8. create a *server.js* file. In this file you will import the packages we just installed:

``` 
const jsonServer = require('json-server');
const server = jsonServer.create();
const router = jsonServer.router('db.json');
const middlewares = jsonServer.defaults();
const port = process.env.PORT || 3000;

server.use(middlewares);
server.use(router);

server.listen(port);
``` 

now we need to write a script in the package.json file: in the object "scripts" you will add another key "start" with the value 'node server.js' ``` "start": "node server.js" ```

> add a .gitignore file if you want to upload your code to github
> ignore node_modules

<hr/>

<div>    
  <img alt="install heroku and create a new project" width="350px" src="https://user-images.githubusercontent.com/95686401/177617967-3921db9c-dd84-49c8-b21e-995df9bb1103.png" /> 
</div>

#### install heroku and create a new project
1. install heroku: in your terminal type the command ``` brew tap heroku/brew && brew install heroku ```
2. ``` npm instal -g heroku --registry https://registry.npmjs.org ```
3. make sure your'e logged in to heroku ``` heroku login ```in your terminal
4. in your terminal: heroku create api-name
> now you have the link of your heroku project!

<hr/>


<div>    
  <img alt="using your api" width="350px" src="https://user-images.githubusercontent.com/95686401/177618276-e053e9cf-dad0-4e4d-b556-2f9bbeb4c8bf.png" /> 
</div>

#### Using your API: 
You can use the database using GET, POST, PUT, DELETE... requests to it. 

```
fetch('https://NAME-OF-YOUR-API.herokuapp.com/OBJECT/0')
  .then(response => response.json())
  .then(data => console.log(data));
```
 
simple as that! 


<div>    
  <img alt="want to help the community? translate this content to your mother language!" src="https://user-images.githubusercontent.com/95686401/177618708-93d1f965-6d91-469e-995d-407e89be1483.png" /> 
</div>

<hr/>

> this is a step by step of how to create your mock api. The content you see here is inspired by [this](https://www.youtube.com/watch?v=FLnxgSZ0DG4&t=272s. ) youtube video from Ania Kubów.
