<div>    
  <img alt="how to create your own api - this is a guide on how to make your own api using JS, node.js and Heroku! Dont forget to star this repository" src="https://user-images.githubusercontent.com/95686401/177616203-2cd9ebd1-0c3f-421b-bb05-587f063a4f3d.png" /> 
</div>


# how to mock a API
This repository was created as a free, open-source guide on how to create your own mock API. When working on a personal project, it can be quite helpful, and you can even post it on gitHub so that others in the community can utilise it. Feel inspired? Atar this repository, so you can always come back and use it!

### clique aqui para acessar o material em PORTUGUÊS 🇧🇷


1. in the folder of your choice, create an database.json file
2. it is inportant to have in mind the 'template' you will be using in this database.
exemple: a chraracter API 

```
{
'characters': [
    {
      'id': 0,
      'name': 'characters name',
      'series': 'the series this character is from',
      'thumbnail': 'image url',
      'description': 'description of the character',
    }
  ]
}
```

> You can modify this example to fit your needs


1. in your terminal, install NPM ``` npm install -g json-server ``` 
>if the response on the terminal says youre blocked: add the npm registry
``` npm install -g json --registry https://registry.npmjs.org ```  
2. then type the command ``` json-server --watch database.json  ``` (the json file you just created) 
3. accsess your database online using the output from your terminal
 > something like https://localhost:3000/YourApiObject


1. create an account or login at heroku
2. deploy the json you created using [heroku](https://www.heroku.com/home)
3. initialize your project: in your terminal type the command ``` npm init ``` 
4. you now have your package.json file
5. now in your terminal type the command ``` npm i ``` 
6. and then ``` npm i json-server --registry https://registry.npmjs.org``` 
7. now your package.json will have a key 'dependencies' with json-server in it and its version.
8. create a *server.js* file. In this file you will import the packages we just installed:

``` 
const jsonServer = require('json-server');
const server = jsonServer.create();
const router = jsonServer.router('database.json'); // the file you created for your database
const middlewares = jsonServer.defaults();
const port = process.env.PORT || 3000;

server.use(middlewares);
server.use(router);
server.listen(port); 
``` 

now we need to write a script in the package.json file: in the object "scripts" you will add another key "start" with the value 'node server.js' ``` "start": "node server.js" ```

> add a .gitignore file if you want to upload your code to github
> ignore node_modules

### install heroku and create a new project
1. install heroku: in your terminal type the command ``` brew tap heroku/brew && brew install heroku ```
2. ``` npm instal -g heroku --registry https://registry.npmjs.org ```
3. make sure your'e logged in to heroku ``` heroku login ```in your terminal
4. in your terminal: heroku create api-name
> now you have the link of your heroku project!

## Using your API: 
You can use the database using GET, POST, PUT, DELETE... requests to it. 

```
fetch('https://NAME-OF-YOUR-API.herokuapp.com/OBJECT/0')
  .then(response => response.json())
  .then(data => console.log(data));
```
 
simple as that! 


> this is a step by step of how to create your mock api. The content you see here is inspired by this youtube video from Ania Kubów https://www.youtube.com/watch?v=FLnxgSZ0DG4&t=272s. 
