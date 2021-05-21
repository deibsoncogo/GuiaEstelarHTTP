# Rocketseat - Guia Estelar de HTTP

Agora iremos aprender sobre o meio de comunicação que uma aplicação web utilizar para falar com o usuário e com ela mesmo e quem vai nos ensinar será o _**Mayk Brito**_ da Rocketseat

>Um assunto fundamental para entendermos como as aplicações web se comunicam com os usuários e também entre si

# Modulo 01 - Entendendo

## Aula 01 - Abertura
O HTTP é um protocolo que permite entender fluxo de mensagens entre cliente e servidor, também vamos ver conceitos sobre URL, URI, mensagens de request e response, métodos, cabeçalhos e outros

## Aula 02 - Visão Geral
HTTP significa **HyperText Transfer Protocol (Protocolo de transferência de HyperTexto)**, com outras palavras iremos falar que é um conjunto de regras formado por palavras que podem conter imagens, vídeos e muito mais

Ele permite trocar informações e dados na internet como HTML, CSS, Scripts, Imagens e outros

## Aula 03 - Visualizando a comunicação
O envio de informações do browser para o servidor é feito por requisições (Request) e o servidor vai responder (Response) algo para o browser

Um **request** possui métodos, um cabeçalho (Headers) e corpo (Body), os métodos define o tipo da requisição onde ler usamos o `get` e para criar o `post`

Um **response** vai ser ter um status com código (Status code) e as vezes um cabeçalho e corpo, os status é a resposta do servidor sobre o request realizado

Um **headers** possui campos informativos no formato de propriedade valor como podemos ver
```ts
name: "Deibson Cogo"
```

Um **body** é utilizado no envio ou recebimento de algum conteúdo num formato especifico como `JSON`

## Aula 04 - Visualizando com DevTools
Um atalho para abrir ele é apertando a tecla F12 dentro do navegador, a partir dele conseguimos ver tudo que aconteceu durante uma nevação em algum site mais para isso temos que ir na aba rede
