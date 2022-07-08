<div>    
  <img alt="como criar sua própria api! esse é um guia de como fazer isso utilizando node.js e heroku como host" src="https://user-images.githubusercontent.com/95686401/177661558-0d7be407-ac22-4454-aca2-f9377b7b69ba.png" /> 
</div>


## como criar sua própria API: 
Esse repositório foi criado para mostrar o passo a passo de como criar uma API e disponibiliza-la ao público. Se gostou do conteúdo, peço que favorite esse repositório! 


<div>    
  <img alt="languages" width="250px" src="https://user-images.githubusercontent.com/95686401/177661767-6b216654-07b4-4ffe-9222-2146813ab958.png" /> 
</div>

#### click [here](https://github.com/calvitoria/how-to-mock-API/blob/main/README.md) to access the content in english 🇬🇧

<hr/>

<div>    
  <img alt="configurações iniciais" width="350px" src="https://user-images.githubusercontent.com/95686401/177661642-0de09ee5-c6ec-4b00-a518-b2aceef42b76.png" /> 
</div>

1. crie o diretório no qual você utilizará para a criação da API.
> Eu aconselho você criar um repositório aqui no github e cloná-lo na sua máquina. Facilitará o último passo do processo.
2. Abra o terminal digite o comando ```npm install``` 
3. digite o comando ```code .``` no terminal se quiser abrir o VScode.
4. Instale o Express: ```npm install express```
5. você deve ter agora uma pasta node_modules e dois arquivos json, o package e package-lock.

<hr/>
<div>    
  <img alt="crie seu banco de dados" width="350px" src="https://user-images.githubusercontent.com/95686401/177661645-a5352a2c-ea0d-4a4b-bec0-8a439c28a6e8.png" /> 
</div>

#### agora vamos começar com nosso arquivo que possui o banco de dados da nossa API!
1. crie um arquivo database.json
> para esse exemplo eu criei uma pasta chamadad src, dentro dela uma pasta chamada characters e dentro dessa última pasta um arquivo (com nosso banco de dados) chamado characters.json (src/characters/characters.json)
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

> Esse é só um exemplo, você pode modificar a estrutura do objeto json como quiser.

<hr/>

<div>    
  <img alt="crie o index.js" width="350px" src="https://user-images.githubusercontent.com/95686401/177661648-447bdd32-8e3f-4faa-8afd-b7fc226db194.png" /> 
</div>

1. crie um arquivo index.js
2. no arquivo, digite o código abaixo: 

```const express = require("express")
const app = express();
const port = process.env.PORT || 3000

const quiz = require("./src/characters/characters.json") // o caminho do nosso arquivo "banco de dados"
app.get("/characters", (req, res) => {
    return res.json(characters)
})

app.listen(port, () => {
    console.log('servidor está rodando...')
})
```
> para se sertificar que está tudo certo, rode no terminal o comando ```node index.js```. "servidor está rodando..." deve aparecer no seu console.
> preste bastante atenção na hora de passar o caminho do seu arquivo database!

3. crie um arquivo .gitignore! esse passo é importantíssimo! se não o fizer, pode acabar dando problema na hora de fazer o deploy da sua API no heroku!

<div>    
  <img alt="edite seu package.json" width="350px" src="https://user-images.githubusercontent.com/95686401/177661748-f4ca9ec6-89f0-4f6e-aae9-bc5bd4618429.png" /> 
</div>

#### agora vamos editar o arquivo package.json
1. em seu arquivo package.json, vamos adicionar o objeto "scripts" com a chave "start" e o valor "node index.js"

```
"scripts": {
  "start": "node index.js"
},

```

seu arquivo deve se parecer com isso:

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
  <img alt="faça o deploy da api" width="350px" src="https://user-images.githubusercontent.com/95686401/177661756-58fd6151-2d9d-474e-a1d7-68d31dc90724.png" /> 
</div>

#### ok, agora é a hora de fazermos o Deploy!
1. crie uma conta ou faça login na plataforma [heroku](https://www.heroku.com/home)
2. no site, crie um novo app, clicando em *new app*. No campo de texto digite o nome da sua api.
3. depois de clicar em *create app* você vai ser direcionado à uma nova página, onde pode escolher como deseja realizar o deploy.
> eu loguei com o github e utilizei essa opção para realizar o deploy; bastou eu procurar o repositório que continha os meus arquivos e conectálo.
4. clique no botão 'open app' para ver a mágica acontecer! Se você deu um endpoint para a resposta json, você vai ter que digitar esse endpoint na url para ter acesso. (no caso do nosso exemplo, ficaria url-direcionada-após-clicar-no-open-app/characters, onde characters é nosso arquivo json que possui todos os nossos dados.

<hr/>

<div>    
  <img alt="Usando sua api" width="350px" src="https://user-images.githubusercontent.com/95686401/177661759-75f59a8c-2cc8-4122-9fa7-4daeba0f3188.png" /> 
</div>

#### Usando sua API: 
agora você pode utilizar os métodos  GET, POST, PUT, DELETE... etc ao fazer requesições à sua própria API! 
Não é incrível?

```
fetch('https://NOME-DA-SUA-API.herokuapp.com/DATABASE') 
  .then(response => response.json())
  .then(data => console.log(data));
```
 
E é isso! simples e rápido!


<div>    
  <img alt="quer ajudar a comunidade? traduza o material para outra língua!" src="https://user-images.githubusercontent.com/95686401/177661770-419e9b1b-16a9-47eb-b245-1390087b0d5c.png" /> 
</div>

<hr/>

> Eu também faço posts educativos no meu [linkedIn](https://www.linkedin.com/in/calvitoria/), dá uma conferida!
> esse passo a passo de como criar uma API foi inspirado no [vídeo](https://www.youtube.com/watch?v=AC62XYv7Yos) produzido pelo canal Stack Mobile no youtube.
