<img alt="GoStack" src="https://storage.googleapis.com/golden-wind/bootcamp-gostack/header-desafios.png" />

<h3 align="center">
  Desafio 02: Conceitos do Node.js
</h3>

## :rocket: Sobre

Essa é uma aplicação feita para o segundo desafio do bootcamp da [@Rocketseat](https://github.com/Rocketseat).

Nesse desafio, foi proposto a criação de uma aplicação para treinar o meu aprendizado sobre rotas no Node.js até o momento.

Essa é uma aplicação para armazenar repositórios do seu portfólio, que permite a criação, listagem, atualização e remoção dos repositórios, e além disso permite que os repositórios possam receber "likes".

### Rotas da aplicação

- **`POST /repositories`**: Recebe `title`, `url` e `techs` dentro do corpo da requisição, sendo a URL o link para o github desse repositório. Ao cadastrar um novo projeto, ele é armazenado dentro de um objeto no seguinte formato: `{ id: "uuid", title: 'Desafio Node.js', url: 'http://github.com/...', techs: ["Node.js", "..."], likes: 0 }`;

- **`GET /repositories`**: Lista todos os repositórios;

- **`PUT /repositories/:id`**: Altera apenas o `title`, a `url` e as `techs` do repositório que possua o `id` igual ao `id` presente nos parâmetros da rota;

- **`DELETE /repositories/:id`**: Deleta o repositório com o `id` presente nos parâmetros da rota;

- **`POST /repositories/:id/like`**: Aumenta o número de likes do repositório específico escolhido através do `id` presente nos parâmetros da rota, a cada chamada dessa rota, o número de likes é aumentado em 1;

### Específicações

- **`able to create a new repository`**: Permite que um repositório seja criado, e retorne um json com o projeto criado.

- **`able to list the repositories`**: Permite que seja retornado um array com todos os repositórios que foram criados até o momento.

- **`able to update repository`**: Permite que sejam alterados apenas os campos `url`, `title` e `techs`.

- **`not able to update a repository that does not exist`**: Validação na rota de update, para verificar se o id do repositório enviado pela url existe ou não. Caso não exista, retornando um erro com status `400`.

- **`not able to update repository likes manually`**: Não permite que a rota de update altere diretamente os likes desse repositório, mantendo assim o mesmo número de likes que o repositório já possuia antes da atualização. Isso porque o único lugar que deve atualizar essa informação é a rota responsável por aumentar o número de likes.

- **`able to delete the repository`**: Permite que a rota de delete exclua um projeto, e ao fazer a exclusão, ele retorna uma resposta vazia, com status `204`.

- **`not able to delete a repository that does not exist`**: Validação na rota de delete, para verificar se o id do repositório enviado pela url existe ou não. Caso não exista, retornando um erro com status `400`.

- **`able to give a like to the repository`**: Permite que um repositório com o id informado receba likes. O valor de likes é incrementado em 1 a cada requisição, e como resultado, retorna um json contendo o repositório com o número de likes atualizado.

- **`not able to like a repository that does not exist`**: Validação na rota de like, para verificar se o id do repositório enviado pela url existe ou não. Caso não exista, retornando um erro com status `400`.
