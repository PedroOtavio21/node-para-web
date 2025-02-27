# Aula 5 - Retornando arquivos estáticos e HTML

## Objetivos da aula

Entender quais são os **arquivos estáticos** de uma aplicação web e **como servi-los de forma eficiente** através do Express

Entender como servir arquivos HTML através de **rotas específicas** no Express

### Configuração do Ambiente

Crie um novo diretório para o projeto.

Abra o terminal e navegue até o diretório do projeto.

Inicie um novo projeto Node.js com `npm init -y`.

### Instalação do Express

Utilize o npm para instalar o Express no projeto com o comando `npm install express`.

### Configuração e Uso de Arquivos Estáticos

Crie uma pasta `public` para armazenar os arquivos estáticos, como **CSS, JS e imagens**.

Utilize o método `express.static()` do Express para **configurar** o uso de arquivos estáticos.

```js
const express = require('express')

const app = express()

app.use(express.static('public'))

const PORT = 3000

app.listen(PORT, () => {
  console.log('Servidor iniciado!')
})
```

### Renderizando Arquivos HTML Estáticos

Crie uma pasta `views` para armazenar os arquivos **HTML estáticos**.

Utilize o método `res.sendFile()` do Express para renderizar um arquivo HTML estático em resposta a uma **requisição**.

```js
// server.js

const express = require('express')

const app = express()

app.use(express.static('public'))

app.get('/', (req, res) => {
  res.sendFile(__dirname + '/views/index.html')
})

const PORT = 3000

app.listen(PORT, () => {
  console.log('Servidor iniciado!')
})
```

```html
<!-- views/index.html -->

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Usando o Express</title>
</head>

<body>
  <h1>Está funcionando!</h1>
  <p>Esta é a nossa página inicial servida através do Express.</p>
</body>

</html>
```

### Criando e Adicionando Arquivos Estáticos

Crie arquivos estáticos, como **style.css** e **script.js** na pasta `public`.

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Usando o Express</title>
  <link rel="stylesheet" href="/assets/style.css">
</head>

<body>
  <h1>Está funcionando!</h1>
  <p>Esta é a nossa página inicial servida através do Express.</p>
  <button id="test">Testar!</button>

  <script src="/assets/script.js"></script>
</body>

</html>
```

```css
body {
  background-color: #1c1a1d;
  color: #fff;
  font-family: sans-serif;
  text-align: center;
  display: grid;
  place-content: center;
}

button {
  cursor: pointer;
  font-size: 1rem;
  padding: 1rem;
}
```

```js
document.getElementById('test').addEventListener('click', () => {
  alert('Este script está funcionando!')
})
```

### Testando o Servidor

Inicie o servidor executando o arquivo `server.js` com o Node.js no **terminal**.

Abra um navegador web e acesse `http://localhost:3000` para verificar se o servidor está respondendo corretamente e servindo os arquivos estáticos.