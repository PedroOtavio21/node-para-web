# Aula 3 - Criando um servidor HTTP

## Objetivos da aula

Entender como funciona um servidor web

Entender por que o Node.js é uma ótima escolha para criar servidores HTTP

Entender como usar o módulo nativo "node:http"

### Configuração do Ambiente

Crie um novo diretório para o projeto.

Abra o terminal e navegue até o diretório do projeto.

Inicie um novo projeto Node.js com `npm init -y`.

### Importando o módulo "node:http"

Criar um arquivo JavaScript (por exemplo, server.js) dentro do diretório do projeto.

Importar o módulo HTTP nativo do Node.js com `const http = require('http');`.

```js
const http = require('node:http')
```

### Criando o Servidor HTTP

Utilizar o método `http.createServer()` para criar um novo servidor.

Passar uma função de callback que será executada sempre que o servidor receber uma requisição.

Na função de callback, enviar uma resposta simples de texto usando `response.write()` e finalizar com `response.end()`.

```js
const server = http.createServer((request, response) => {
  console.log(request)
  response.writeHead(200)
  response.write('Servidor HTTP em Node.js funcionando!')
  response.end()
})
```

### Configurando e Iniciando o Servidor

Definir a porta em que o servidor irá escutar, por exemplo, const `port = 3000;`.

Utilizar o método `server.listen()` para fazer o servidor escutar as requisições na porta especificada.

```js
const PORT = 3000

server.listen(PORT, () => {
  console.log(`Servidor rodando em <http://localhost>:${PORT}/`)
})
```

### Adicionando uma Rota Simples

Criar uma rota que responda com uma mensagem específica quando acessada.

Verificar o caminho da requisição usando `request.url`.

Adicionar uma condição para verificar se o caminho da requisição corresponde à rota desejada e, em seguida, enviar a resposta correspondente.

```js
const server = http.createServer((request, response) => {
  const path = request.url

  switch (path) {
    case '/':
      response.writeHead(200)
      response.write('Você está na página inicial!')
      break;
    case '/artigos':
      response.writeHead(200)
      response.write('Você está na página "artigos"!')
      break;
    default:
      response.writeHead(404)
      response.write('Caminho não encontrado!')
      break;
  }

  response.end()
})
```