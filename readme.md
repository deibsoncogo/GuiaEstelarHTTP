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

## Aula 05 - Visualizando com cURL
O `cURL` é uma ferramenta que vai permitir ver todas informações que um protocolo possui, ele vem instalado no `Git Bash`

Para executar uma requisição simples usamos este comando
```bash
curl https://google.com
```

Para retornar os headers das respostas adicionamos um item no comando
```bash
curl -i https://google.com
```

Para retornar todos headers temos que trocar um item no comando, onde os itens que começarem com `*` serão informações de conexão, os com `>` é informações relacionado ao request e com `<` do response
```bash
curl -v https://google.com
```

# Modulo 02 - Conceitos

## Aula 06 - Conceitos
Ele criado para ser legível e utilizado por qualquer pessoa, tudo é realizado entre o cliente e servidor por requisição e resposta (Request ou response), ele não salva estado dos itens pois ele é um **stateless** mais possui a funções de sessões por exemplo cookies e storage, ele também é extensível onde pelo cabeçalho podemos realizar diversas trocas de informações

## Aula 07 - Cliente
O cliente é user agent onde na maioria das vezes é o browser que funciona a partir de pedido de métodos como `get`, `post`, `put` e `delete` (São os mais utilizados)

## Aula 08 - Servidor
O servidor é uma máquina em algum ligar no mundo esperando um pedido do cliente, um computador pode estar conectado a diversos servidores ao mesmo tempo, sua função é responder algo como um status code
