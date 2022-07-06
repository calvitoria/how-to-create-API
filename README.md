<div>    
  <img alt="how to create your own api - this is a guide on how to make your own api using JS, node.js and Heroku! Dont forget to star this repository" src="https://user-images.githubusercontent.com/95686401/177621091-81b2355f-eff5-467d-a81b-3bdec466baba.png" /> 
</div>


## how to create your own API: 
Esse repositório foi criado para mostrar o passo a passo de como criar uma API e disponibiliza-la ao público. Se gostou do conteúdo, peço que favorite esse repositório! 


<div>    
  <img alt="languages" width="250px" src="https://user-images.githubusercontent.com/95686401/177618703-b3400ec7-50ed-4b4e-941d-147437af7ab2.png" /> 
</div>

### clique [aqui](https://github.com/calvitoria/how-to-mock-API/blob/main/README.md) para acessar o material em inglês 🇬🇧

<hr/>

<div>    
  <img alt="configurações iniciais" width="350px" src="https://user-images.githubusercontent.com/95686401/177658129-530cf712-dabe-4b4f-af06-03a9063f529f.png" /> 
</div>

1. crie o diretório no qual você utilizará para a criação da API.
> Eu aconselho você criar um repositório aqui no github e cloná-lo na sua máquina. Facilitará o último passo do processo.
2. Abra o terminal digite o comando ```npm install``` 
3. digite o comando ```code .``` no terminal se quiser abrir o VScode.
4. Instale o Express: ```npm install express```
5. você deve ter agora uma pasta node_modules e dois arquivos json, o package e package-lock.

<hr/>
<div>    
  <img alt="crie seu banco de dados" width="350px" src="https://user-images.githubusercontent.com/95686401/177658177-616660e3-7106-4ba6-bcc0-0cfa1f18cb25.png" /> 
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
  <img alt="crie o index.js" width="350px" src="https://user-images.githubusercontent.com/95686401/177658207-901e3cd6-85b1-43a7-878f-7ec338ab4520.png" /> 
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
  <img alt="edite seu package.json" width="350px" src="https://user-images.githubusercontent.com/95686401/177658247-5f6220ca-03d8-4bd3-b12f-9e45a44763d3.png" /> 
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
  <img alt="deploy your database" width="350px" src="https://user-images.githubusercontent.com/95686401/177658275-c0a1a02f-c92f-4a2c-99d7-3b30529eb4c0.png" /> 
</div>

#### ok, agora é a hora de fazermos o Deploy!
1. crie uma conta ou faça login na plataforma [heroku](https://www.heroku.com/home)
2. no site, crie um novo app, clicando em *new app*. No campo de texto digite o nome da sua api.
3. depois de clicar em *create app* você vai ser direcionado à uma nova página, onde pode escolher como deseja realizar o deploy.
> eu loguei com o github e utilizei essa opção para realizar o deploy; bastou eu procurar o repositório que continha os meus arquivos e conectálo.
4. clique no botão 'open app' para ver a mágica acontecer! Se você deu um endpoint para a resposta json, você vai ter que digitar esse endpoint na url para ter acesso. (no caso do nosso exemplo, ficaria url-direcionada-após-clicar-no-open-app/characters, onde characters é nosso arquivo json que possui todos os nossos dados.

<hr/>

<div>    
  <img alt="Usando sua api" width="350px" src="https://user-images.githubusercontent.com/95686401/177618276-e053e9cf-dad0-4e4d-b556-2f9bbeb4c8bf.png" /> 
</div>

#### Usando sua API: 
agora você pode utilizar os métodos  GET, POST, PUT, DELETE... etc ao fazer requesições à sua própria API! 
Não é incrível?

```
fetch('https://NAME-OF-YOUR-API.herokuapp.com/DATABASE') 
  .then(response => response.json())
  .then(data => console.log(data));
```
 
E é isso! simples e rápido!


<div>    
  <img alt="quer ajudar a comunidade? traduza o material para outra língua!" src="https://user-images.githubusercontent.com/95686401/177618708-93d1f965-6d91-469e-995d-407e89be1483.png" /> 
</div>

<hr/>

> Eu também faço posts educativos no meu [linkedIn](https://www.linkedin.com/in/calvitoria/), dá uma conferida!
> esse passo a passo de como criar uma API foi inspirado no [vídeo](https://www.youtube.com/watch?v=AC62XYv7Yos) produzido pelo canal Stack Mobile no youtube.
