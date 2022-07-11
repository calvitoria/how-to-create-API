<div>    
  <img alt="how to create your own api - this is a guide on how to make your own api using JS, node.js and Heroku! Dont forget to star this repository" src="https://user-images.githubusercontent.com/99758843/177888023-a2e43bcc-eb31-4270-9f64-06ae1eaeb3b2.png" />
</div>

## comment créer votre propre API:
Ce dépôt a été créé comme un guide gratuit et open-source sur la façon de créer votre propre API et de l'héberger. Lorsqu'on travaille sur un projet personnel, il peut être très utile, et vous pouvez même le poster sur gitHub pour que d'autres membres de la communauté puissent l'utiliser. Vous vous sentez inspiré ? Atar ce dépôt, de sorte que vous pouvez toujours revenir et l'utiliser!

<div>    
  <img alt="languages" width="250px" src="https://user-images.githubusercontent.com/99758843/177888035-11a0a34a-760d-4ca7-a6dd-f4f907105de5.png" />
</div>

### clique [aqui](https://github.com/calvitoria/how-to-mock-API/blob/portuguese-language/README.md) para acessar o material em português 🇧🇷

### click [here](https://github.com/calvitoria/how-to-create-API/blob/main/README.md) to access the material in English :gb:

<hr/>

<div>    
  <img alt="before starting, initial configuration" width="350px" src="https://user-images.githubusercontent.com/99758843/177888024-68b5c718-b9d6-41ff-b2da-29c2f237a90b.png" />
</div>

1. Créez le répertoire dans lequel vous souhaitez placer vos fichiers.
> Je vous encourage à créer un dépôt github et à le cloner, afin de pouvoir déployer dans Heroku en utilisant ce dépôt exact.
2. Ouvrez votre terminal et installez npm : ``npm install``.
3. tapez ``code .`` dans votre terminal pour ouvrir VScode.
4. Installez Express: ``npm install express``
5. vous devriez maintenant avoir un dossier node_modules, un fichier package.json et un package-lock.json.

<hr/>

<div>    
  <img alt="1. create your database" width="350px" src="https://user-images.githubusercontent.com/99758843/177888025-38e956eb-bcd2-4e3f-9509-39e328635a07.png" /> 
</div>

#### commençons par notre fichier databasa:
1. Dans le dossier de votre choix, créez un fichier database.json.
> dans cet exemple, j'ai créé un dossier src et un dossier characters à l'intérieur de celui-ci, avec le database.js à l'intérieur de ce dossier.
(path: src/characters/characters.json)
2. il est important d'avoir à l'esprit le 'template' que vous allez utiliser dans cette base de données.
exemple: un chraracter API

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

> Vous pouvez modifier cet exemple pour l'adapter à vos besoins.

<hr/>

<div>    
  <img alt="create your index.js file" width="350px" src="https://user-images.githubusercontent.com/99758843/177888026-4e071b86-a6f8-4f4a-8d15-60dd4b72ec76.png" />
</div>

1. créez un fichier index.js
2. dans votre fichier index.js, tapez le code suivant:

```
const express = require("express")
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
> pour vérifier si tout est bon et fonctionne, tapez dans votre terminal ``node index.js`` le console.log devrait s'imprimer.
> faites attention au path de vos fichiers!

3. créez un fichier .gitignore et ajoutez-y node_modules. ! c'est vraiment important ! pour faire un déploiement vers Heroku, vous ne devez PAS télécharger node_modules avec le reste de vos fichiers.

<div>    
  <img alt="edit your package.json" width="350px" src="https://user-images.githubusercontent.com/99758843/177888028-017f70a4-0361-4fd0-8260-877f47da495e.png" />
</div>

#### maintenant éditons notre package.json
1. Dans votre fichier package.json, ajoutez l'objet "scripts" avec la clé "start" et la valeur "node index.js".

```
"scripts": {
  "start": "node index.js"
},

```

votre fichier package.json devrait ressembler à ceci:

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
  <img alt="deploy your database" width="350px" src="https://user-images.githubusercontent.com/99758843/177888029-9ed445dd-0bd6-43ce-a220-eb47ee3fbbf0.png" />
</div>

#### ok, maintenant nous devons déployer notre API
1. créer un compte ou se connecter à [heroku](https://www.heroku.com/home)
2. sur le site heroku, créez une *new app*. Donnez-lui le nom de votre API.
3. après avoir cliqué sur "create app", vous serez redirigé vers une nouvelle page, où vous pouvez choisir comment vous allez déployer votre API.

> J'ai utilisé la méthode Github. Il suffit de se connecter, de choisir le dépôt auquel vous allez vous connecter et de choisir le mode de déploiement.

4. utilisez le bouton 'open app' pour voir la magie ! Selon la façon dont vous avez créé vos fichiers, vous devrez peut-être aussi saisir le point de terminaison de votre base de données.

> Si vous construisez votre application comme je l'ai fait, cliquer simplement sur le bouton ne sera pas suffisant ! Vous devrez taper dans l'URL le endpoint de votre json.

<hr/>

<div>    
  <img alt="using your api" width="350px" src="https://user-images.githubusercontent.com/99758843/177888032-07613f66-0b31-44e2-b677-7c43cf221c15.png" />
</div>

#### Utilisation de votre API:
Vous pouvez utiliser la base de données en lui envoyant des requêtes GET, POST, PUT, DELETE...

```
fetch('https://NAME-OF-YOUR-API.herokuapp.com/DATABASE') 
  .then(response => response.json())
  .then(data => console.log(data));
```
 
C'est aussi simple que cela!

<div>    
  <img alt="want to help the community? translate this content to your mother language!" src="https://user-images.githubusercontent.com/99758843/177888036-b36a2ee3-a4b5-41f9-9e21-c0569af166b7.png" />
</div>

Si vous êtes intéressé à contribuer à ce projet, vous pouvez simplement cloner le dépôt, ouvrir une nouvelle branche comme ``"________-language"``, puis suivre la structure du README. Si vous voulez ajouter les images d'en-tête, vous pouvez faire une copie de [cette](https://www.canva.com/design/DAFFwQQCaxw/8xlYGBJfRGUvEMcrQ1bn-g/edit?utm_content=DA[...]m_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
sur Canva et modifiez-le. Si vous n'en avez pas envie, pas d'inquiétude ! Il suffit de créer un titre normal pour chaque étape ! Si vous voulez utiliser le modèle de Canva, vous pouvez utiliser les issues de Github pour transformer le fichier png en URL.
