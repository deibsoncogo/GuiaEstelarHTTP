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

## Aula 09 - Proxies
Os proxies possuem a função de ser um representando onde ele fica entre o cliente e o servidor ajudando a transportar os dados, um exemplo seria o roteador de internet que temos em casa, existe diversas funções para ele como criação de cache, filtro (Regra de acesso), autenticação e outros

# Modulo 03 - URI

## Aula 10 - Resource
O `Uniform Resource Identifier (URI)` é um identificador de forma uniforme que vai identificar o recurso pelo nome ou localização

## Aula 11 - Recurso
O recurso é o alvo do pedido, ele é qualquer coisa identificável (Entidade), ela possui algumas formas como **digital** que seria um email representado assim `mailto:teste@email.com.br`, a forma **abstrata** seria uma sessão ou autenticação e a última é a **física** como produtos ou usuários

## Aula 12 - URL
`Uniform Resource Locator` é um tipo de localizador pelo endereço, ela deve conter estes itens
  * Protocolo: É a primeira coisa do endereço (https)
  * Domínio: Seria o endereço do site (rocketseat.com.br)

Também temos alguns itens que são opcionais onde quando utilizamos ele se torna fundamental
  * Subdomínio: Vem antes do domínio (www)
  * Path: É tudo que vem depois do domínio (/blog)
  * Parâmetro: É identificado por uma interrogação, chave e um valor (?chave=valor)
  * Porta: Uma porta é identificada por dois pontos (:3333)
  * Âncora: É reconhecido pela hashtag onde nos leva para alguma parte do site (#lugar)

O protocolo `http` usa a porta 80 quando não informamos uma e o `https` a 443

```bash
// exemplos de URL completos
https://www.rocketseat.com.br/blog
https://www.youtube.com/watch?v=vpYct2npKD8
http://127.0.0.1:3333/index.html#algumlugar
```

## Aula 13 - URN
`Uniform Resource Name` é um tipo de localizador pelo nome do local, temos este exemplo da aplicação
```bash
urn:isbn:0451450523
urn:oasis:names:specification:doc:dtd:xml:4.1.2
```

## Aula 14 - Revisão resource
A URN quase não será utilizada já a URL iremos usar muito

# Modulo 04 - Messages

## Aula 15 - Mensagens
Toda comunicação é feita por mensagens a partir da versão 1.1 do HTTP de forma bem legível e textual, já na versão 2 ela possui uma estrutura binária permitindo otimizações

## Aula 16 - Request
O pedido possui um método baseado em um protocolo e URI, algumas vezes enviamos body e headers

## Aula 17 - Response
A resposta vai possuir o protocolo, status code, headers e status message

# Modulo 05 - Methods

## Aula 18 - Introdução
Existe diversos métodos e verbos HTTP que podemos usar onde os principais iremos estudar

## Aula 19 - Methods
Uma definição de conjunto de métodos HTTP é que cada um indica a ação que o cliente deseja operar, também podemos chamar de verbos HTTP, cada um possui a seu significado

Alguns são **seguros** pois alguns servem para realizar consultas (GET, HEAD e OPTIONS) e outros são **idempotente** pois ao executar o método a resposta deverá ser sempre a mesmo (PUT, DELETE, GET, HEAD e OPTIONS) mais o status code pode mudar

## Aula 20 - JSON Server
Para executar os testes vamos precisar instalar a dependência [JSON-Server](https://github.com/typicode/json-server) de forma global
```bash
npm install -g json-server
```

Para quem não quiser instalar ele temos o `JSONPlaceholder` para utilizar

## Aula 21 - Options
Ele serve para informar quais métodos estão disponíveis em uma rota especifica
  * [X] Seguro (Se não altera as informações)
  * [X] Idempotente (Se sempre teremos a mesma resposta)
  * [ ] Request (Se possui uma requisição)
  * [ ] Response (Se possui uma resposta)
  * [ ] Formulário (Se é utilizado em formulários)
  * [ ] Cacheable (Se podemos criar cache com ele)

## Aula 22 - Get
Este método serve para recuperar as informações de um recurso
  * [X] Seguro (Se não altera as informações)
  * [X] Idempotente (Se sempre teremos a mesma resposta)
  * [ ] Request (Se possui uma requisição)
  * [X] Response (Se possui uma resposta)
  * [X] Formulário (Se é utilizado em formulários)
  * [X] Cacheable (Se podemos criar cache com ele)


## Aula 23 - Head
Ele é parecido ao método `get` mais ele recebe somente o cabeçalho
  * [X] Seguro (Se não altera as informações)
  * [X] Idempotente (Se sempre teremos a mesma resposta)
  * [ ] Request (Se possui uma requisição)
  * [ ] Response (Se possui uma resposta)
  * [ ] Formulário (Se é utilizado em formulários)
  * [X] Cacheable (Se podemos criar cache com ele)

## Aula 24 - Post
Ele é utilizar para cadastrar um novo recurso
  * [ ] Seguro (Se não altera alguma informação)
  * [ ] Idempotente (Se sempre teremos o mesmo tipo de retorno)
  * [X] Request (Se possui uma requisição)
  * [X] Response (Se possui uma resposta)
  * [X] Formulário (Se é utilizado em formulários)
  * [X] Cacheable (Se podemos criar cache com ele)

## Aula 25 - Put
Podemos utilizar para criar um recurso ou alterar
  * [ ] Seguro (Se não altera alguma informação)
  * [X] Idempotente (Se sempre teremos o mesmo tipo de retorno)
  * [X] Request (Se possui uma requisição)
  * [ ] Response (Se possui uma resposta)
  * [ ] Formulário (Se é utilizado em formulários)
  * [ ] Cacheable (Se podemos criar cache com ele)

## Aula 26 - Patch
Ele serve para realizar uma modificação parcial de algo
  * [ ] Seguro (Se não altera alguma informação)
  * [ ] Idempotente (Se sempre teremos o mesmo tipo de retorno)
  * [X] Request (Se possui uma requisição)
  * [X] Response (Se possui uma resposta)
  * [ ] Formulário (Se é utilizado em formulários)
  * [ ] Cacheable (Se podemos criar cache com ele)

## Aula 27 - Delete
Usamos ele para remover um recurso/informação
  * [ ] Seguro (Se não altera alguma informação)
  * [X] Idempotente (Se sempre teremos o mesmo tipo de retorno)
  * [X] Request (Se possui uma requisição)
  * [X] Response (Se possui uma resposta)
  * [ ] Formulário (Se é utilizado em formulários)
  * [ ] Cacheable (Se podemos criar cache com ele)

# Modulo 06 - Headers

## Aula 28 - O que são Headers?
Sua tradução é cabeçalhos, onde são informações adicionais utilizado no resquest ou no response
Ele funciona no esquema de nome e valor

## Aula 29 - Entendendo pelo contexto
Existe diversos headers e para deixar dinâmico a explicação iremos dividir eles em três contextos como general, request headers e response headers.

## Aula 30 - General
Os contextos `servem` podem ser utilizado tanto pelo resquest ou response
Ele contem o URL utilizada, o método, o status code, o remote address e outros
