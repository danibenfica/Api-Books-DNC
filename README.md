# API de Cadastro de Livros

## Introdução

Esta é uma API de cadastro de livros que permite a gestão de informações sobre livros, incluindo id, título, número de páginas, ISBN e editora.

## Estrutura de Pastas e Arquivos

### Principais arquivos:

- **models**: Contém o arquivo `Livro.js`, que define o esquema do modelo de dados para os livros.
- **envExemplo.txt**: Um exemplo de como configurar o arquivo `.env`.
- **server.js**: O arquivo principal que controla a API.

## Requisitos de Instalação

Antes de iniciar o projeto, certifique-se de ter o Node.js e o npm (gerenciador de pacotes do Node.js) instalados em seu sistema. Você pode fazer o download do Node.js em [nodejs.org](https://nodejs.org/).

## Instalação das Dependências

Para instalar todas as dependências necessárias, siga estas etapas:

1. Abra o terminal na raiz do projeto.

2. Execute o seguinte comando para instalar as dependências:

   ```bash
   npm install
   ```

   Isso instalará todas as dependências listadas no arquivo `package.json`, incluindo o `nodemon`, que é usado para reiniciar automaticamente o servidor durante o desenvolvimento.

## Iniciar o Servidor com nodemon

Para iniciar o servidor usando `nodemon`, basta executar o seguinte comando no terminal:

```bash
npm start
```

Isso iniciará o servidor e o manterá em execução, monitorando automaticamente os arquivos do projeto. Sempre que você fizer alterações em qualquer um dos arquivos, o `nodemon` reiniciará automaticamente o servidor para refletir essas alterações.

Lembre-se de que o `nodemon` deve ser usado apenas em ambientes de desenvolvimento, e não em produção.

## Modelo de Dados

O modelo de dados para os livros é definido no arquivo `Livro.js` no diretório `models`. O modelo possui os seguintes campos:

- `_id` (String): Identificador único do livro.
- `titulo` (String): Título do livro.
- `num_paginas` (Number): Número de páginas do livro.
- `isbn` (String): Número ISBN do livro.
- `editora` (String): Editora do livro.

## Configuração da Conexão com o Banco de Dados

Para configurar a conexão com o banco de dados MongoDB, crie um arquivo `.env` na raiz do projeto e adicione o link de conexão da seguinte forma:

```env
MONGODB_URI=mongodb+srv://seuUsuario:suaSenha@apibooks.xscvmrg.mongodb.net/sua_base_de_dados?retryWrites=true&w=majority
```

Substitua `seuUsuario`, `suaSenha` e `sua_base_de_dados` pelos detalhes da sua configuração do MongoDB.

## API Endpoints

A API possui os seguintes endpoints:

### GET /livros

Este endpoint retorna todos os livros cadastrados.

**Exemplo de Requisição:**
```http
GET /livros
```

**Exemplo de Resposta (200 OK):**
```json
[
  {
    "_id": "1",
    "titulo": "Os Imortais",
    "num_paginas": 352,
    "isbn": "978-85-7555-788-6",
    "editora": "Intrínseca"
  },
  {
    "_id": "2",
    "titulo": "A Garota no Trem",
    "num_paginas": 378,
    "isbn": "978-85-8057-902-9",
    "editora": "Record"
  },
  {
    "_id": "3",
    "titulo": "Extraordinário",
    "num_paginas": 320,
    "isbn": "978-85-64809-77-0",
    "editora": "Intrínseca"
  }
]
```

### GET /livros/:id

Este endpoint retorna um livro específico com base no ID fornecido.

**Exemplo de Requisição:**
```http
GET /livros/2
```

**Exemplo de Resposta (200 OK):**
```json
{
  "_id": "2",
  "titulo": "A Garota no Trem",
  "num_paginas": 378,
  "isbn": "978-85-8057-902-9",
  "editora": "Record"
}
```

### POST /livros

Este endpoint cria um novo livro com os dados fornecidos no corpo da requisição.

**Exemplo de Requisição:**
```http
POST /livros
Content-Type: application/json

{
  "titulo": "1984",
  "num_paginas": 328,
  "isbn": "978-0-452-28423-4",
  "editora": "Companhia das Letras"
}
```

**Exemplo de Resposta (201 Created):**
```json
{
  "_id": "4",
  "titulo": "1984",
  "num_paginas": 328,
  "isbn": "978-0-452-28423-4",
  "editora": "Companhia das Letras"
}
```

### PUT /livros/:id

Este endpoint atualiza um livro existente com base no ID fornecido e os dados no corpo da requisição.

**Exemplo de Requisição:**
```http
PUT /livros/2
Content-Type: application/json

{
  "titulo": "Harry Potter e a Câmara Secreta",
  "editora": "Rocco

"
}
```

**Exemplo de Resposta (200 OK):**
```json
{
  "_id": "2",
  "titulo": "Harry Potter e a Câmara Secreta",
  "num_paginas": 378,
  "isbn": "978-85-325-1525-0",
  "editora": "Rocco"
}
```

### DELETE /livros/:id

Este endpoint exclui um livro com base no ID fornecido.

**Exemplo de Requisição:**
```http
DELETE /livros/3
```

**Exemplo de Resposta (200 OK):**
```json
{
  "message": "Livro excluído com sucesso",
  "id": "3",
  "titulo": "Extraordinário"
}
```

## Conclusão

Esta documentação fornece uma visão geral da estrutura e funcionamento da API de cadastro de livros. Não se esqueça de configurar a conexão com o Mongo ntes de iniciar o servidor.
É uma aplicação bem simples e foi desenvolvida par ao desafio 5 do curso da DNC!

Caso tenha dúvidas ou sugestões de como posso melhorar meu projeto, não hesite em entrar em contato! :heart:
