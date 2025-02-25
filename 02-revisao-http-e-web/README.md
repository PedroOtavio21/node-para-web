# Aula 2 - Revisão: HTTP e Programação Web

## O que é HTTP?
Principal protocolo usado na web

Protocolo de comunicaão baseado em **requisições** e **respostas**

Define como cliente e servidor devem interagir, além do formato e modo de transmissçao das mensagens entre eles

Revisando os principais métodos:
- GET: Indica intenção de leitura ou obtenção dos dados
- POST: Indica intenção de envio de dados, seja para persistência ou outros fins
- PUT/PATCH: Indica intenção de atualização ou correção de dados no servidor
- DELETE: Indica intenção de dados no servidor

Revisando os principais status:
- 200 e variações: (200 - Sucesso, mas genérico; 201 - Criado; 202 - Aceito; 204 - Sucesso, porém nenhum conteúdo; 206 - Conteúdo parcial)
- 300 e variações: Redirecionamento (301 - Movido permanentemente)
- 400 e variações: Problemas na requisição (400 - Requisição ruim/incorreta, mas genérico; 401 - Não autorizado; 402 - Proibido; 401 - Não encontrado; 405 - Método não permitido; 408 - *Timeout*, ou tempo esgotado)
- 500 e variações: (500 - Erro interno no servidor, mas genérico; 501 - Não implementado; 503 - Serviço indisponível)
- [Revise os códigos](https://http.dog/);

## Como é utilizado na prática?
Navegadores enviam requisições (principalmente GET e POST) e o backend as recebe, interpreta e envia uma **respost** (um arquivo HTML ou JSON, por exemplo)

Ao desenvolvermos aplicações para servidores web (o "backend" de um app, por exemplo), implementamos esse protocolo na comunicação

É importante seguir as regras e conceitos do HTTP, pois é o formato que será usado pelos navegadores

## O que faz um programador web?
O programador web atua tanto desenvolvendo as páginas que farão as requisições (frontend) quanto as aplicações no servidor para respondê-las (backend)

Hoje, graças a evolução da web e suas tecnologias, é possível se especializar em um desses segmentos

## Onde entra o Node.js?
O Node.js permite trabalhar com JavaScript fora do navegador (nesse caso, no lado do servidor/backend)

Com isso, se torna uma ferramenta excelente para criar servidores HTTP e APIs no backend

Esse e outros fatores contribuiram para que o Node.js evoluísse muito nessa direção e se tornasse uma das melhores opções desse mercado