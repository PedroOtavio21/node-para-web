# Aula 4 - Conhecendo o Express

## Objetivos da aula

Entender o que é um framework

Entender como usar o Express e seu sistema de rotas

Entender por que o Express é uma boa escolha para desenvolvimento de aplicações web

Descrição da facilidade de uso e flexibilidade oferecida pelo Express para lidar com rotas e requisições HTTP.

### Configuração do Ambiente

Crie um novo diretório para o projeto.

Abra o terminal e navegue até o diretório do projeto.

Inicie um novo projeto Node.js com npm `init -y`.

### Instalação do Express

Utilizar o npm para instalar o Express no projeto com o comando `npm install express`

### Importando o Express e criando o servidor

Importar o módulo Express no arquivo principal do projeto.

Criar uma instância do aplicativo Express com `express()`.

Definir uma rota raiz que responda com uma mensagem simples.

```js
const express = require('express')

const server = express()

server.get('/', (request, response) => {
  response.send('Servidor Express funcionando!\\nVocê está na página inicial.')
})

const PORT = 3000

server.listen(PORT, () => {
  console.log(`Servidor Express iniciado em <http://localhost>:${PORT}/`)
})
```

### Adicionando uma rota de forma simples

Criar uma nova rota que responda com uma mensagem específica.

Utilizar o método `server.get()` para definir a rota e a resposta associada.

```js
const express = require('express')

const server = express()

server.get('/', (request, response) => {
  response.send('Servidor Express funcionando!\\nVocê está na página inicial.')
})

server.get('/artigos', (req, res) => {
  res.send('Você está na página "artigos".')
})

const PORT = 3000

server.listen(PORT, () => {
  console.log(`Servidor Express iniciado em <http://localhost>:${PORT}/`)
})
```

### Testando o Servidor

Iniciar o servidor executando o arquivo server.js com o Node.js no terminal.

Abrir um navegador web e acessar http://localhost:3000 para verificar se o servidor está respondendo corretamente.

Testar também a rota adicionada, acessando http://localhost:3000/artigos.