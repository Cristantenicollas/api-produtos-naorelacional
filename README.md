# 🛒 API de Produtos — Banco de Dados Não Relacional

> 🚀 API REST desenvolvida em Node.js para gerenciamento de produtos, utilizando MongoDB como banco de dados não relacional.

## 📌 Sobre o Projeto

O projeto **API Produtos Não Relacional** consiste em uma aplicação backend desenvolvida com Node.js e Express, integrada ao MongoDB para realizar operações de gerenciamento de produtos.

A aplicação disponibiliza endpoints HTTP que permitem cadastrar, consultar, atualizar e excluir produtos armazenados no banco de dados.

O objetivo do projeto é aplicar conceitos de desenvolvimento de APIs REST, integração com bancos de dados NoSQL e manipulação de dados utilizando operações CRUD.

## ⚙️ Tecnologias Utilizadas

- **Node.js** — Ambiente de execução JavaScript no backend.
- **Express.js** — Framework utilizado para criação e gerenciamento das rotas HTTP.
- **MongoDB** — Banco de dados não relacional (NoSQL).
- **MongoDB Node.js Driver** — Biblioteca responsável pela comunicação com o banco de dados.
- **JavaScript** — Linguagem utilizada no desenvolvimento da aplicação.
- **Git e GitHub** — Controle de versão e hospedagem do código-fonte.

## ✨ Funcionalidades

A API possui as seguintes funcionalidades:

### 📦 Gerenciamento de Produtos

- **Cadastrar produtos:** permite inserir novos produtos no banco de dados.
- **Listar produtos:** retorna todos os produtos cadastrados.
- **Consultar produto por ID:** permite localizar um produto específico através do seu identificador.
- **Atualizar produtos:** permite modificar as informações de um produto existente.
- **Excluir produtos:** permite remover um produto do banco de dados.

### 🔄 Operações CRUD

A aplicação implementa as quatro operações fundamentais de manipulação de dados:

| Operação | Método HTTP | Endpoint |
|---|---|---|
| Create | POST | `/produtos` |
| Read | GET | `/produtos` |
| Read por ID | GET | `/produtos/:id` |
| Update | PUT | `/produtos/:id` |
| Delete | DELETE | `/produtos/:id` |

## 📁 Estrutura do Projeto

```text
api-produtos-naorelacional/
│
├── index.js
├── package.json
├── package-lock.json
└── .gitignore
```

### Descrição dos Arquivos

- **index.js:** arquivo principal da aplicação, responsável por configurar o Express, estabelecer a conexão com o MongoDB e definir as rotas da API.
- **package.json:** contém as informações do projeto e suas dependências.
- **package-lock.json:** registra as versões específicas das dependências instaladas.
- **.gitignore:** define os arquivos e diretórios que não devem ser enviados ao repositório Git.

## 💻 Como Executar o Projeto

### 1. Pré-requisitos

Antes de iniciar, é necessário ter instalado:

- [Node.js](https://nodejs.org/)
- [MongoDB Atlas](https://www.mongodb.com/products/platform/atlas) ou uma instância local do MongoDB.
- [Git](https://git-scm.com/)

### 2. Clonar o Repositório

Abra o terminal e execute:

```bash
git clone https://github.com/Cristantenicollas/api-produtos-naorelacional.git
```

Entre na pasta do projeto:

```bash
cd api-produtos-naorelacional
```

### 3. Instalar as Dependências

Execute o comando:

```bash
npm install
```

Esse comando instala as bibliotecas necessárias para executar a aplicação, incluindo Express e MongoDB.

### 4. Configurar a Conexão com o MongoDB

A aplicação utiliza a variável de ambiente `MONGO_URI` para estabelecer a conexão com o banco de dados.

Configure essa variável com a sua string de conexão do MongoDB.

**Windows PowerShell:**

```powershell
$env:MONGO_URI="SUA_STRING_DE_CONEXAO_MONGODB"
```

**Linux / macOS:**

```bash
export MONGO_URI="SUA_STRING_DE_CONEXAO_MONGODB"
```

Substitua `SUA_STRING_DE_CONEXAO_MONGODB` pela string de conexão válida do seu banco de dados.

O banco utilizado pela aplicação é `loja`, e a coleção utilizada para armazenar os registros é `produtos`.

### 5. Executar a Aplicação

Após configurar a conexão, execute:

```bash
node index.js
```

Se a conexão for estabelecida corretamente, serão exibidas as mensagens:

```text
CONECTADO AO MONGODB COM SUCESSO!
API RODANDO NA PORTA 3000
```

A API estará disponível em:

```text
http://localhost:3000
```

## 🌐 Endpoints da API

Os endpoints podem ser testados utilizando ferramentas como Postman ou Insomnia.

### 1. Cadastrar Produto

**Método:** `POST`

**Endpoint:**
```http
http://localhost:3000/produtos
```

Insira os dados do produto no corpo da requisição, utilizando JSON.

Exemplo:

```json
{
    "nome": "Mouse Gamer",
    "preco": 149.90,
    "categoria": "Periféricos"
}
```

### 2. Listar Todos os Produtos

**Método:** `GET`

**Endpoint:**
```http
http://localhost:3000/produtos
```

Retorna uma lista contendo todos os produtos cadastrados na coleção.

### 3. Consultar Produto por ID

**Método:** `GET`

**Endpoint:**
```http
http://localhost:3000/produtos/ID_DO_PRODUTO
```

Retorna as informações do produto correspondente ao identificador informado.

### 4. Atualizar Produto

**Método:** `PUT`

**Endpoint:**
```http
http://localhost:3000/produtos/ID_DO_PRODUTO
```

Permite atualizar as informações de um produto existente.

Exemplo de corpo da requisição:

```json
{
    "nome": "Mouse Gamer RGB",
    "preco": 179.90
}
```

### 5. Excluir Produto

**Método:** `DELETE`

**Endpoint:**
```http
http://localhost:3000/produtos/ID_DO_PRODUTO
```

Remove o produto correspondente ao identificador informado.

## 🗄️ Banco de Dados

O projeto utiliza o **MongoDB**, um banco de dados não relacional que trabalha com documentos no formato BSON, permitindo armazenar informações de maneira flexível.

A estrutura utilizada na aplicação é:

```text
MongoDB
   │
   └── Banco: loja
          │
          └── Coleção: produtos
                  │
                  ├── Produto 1
                  ├── Produto 2
                  └── Produto 3
```

Os produtos são armazenados como documentos dentro da coleção `produtos`, e cada registro recebe automaticamente um identificador único `_id` gerado pelo MongoDB.

## 🔐 Configuração e Segurança

A string de conexão do MongoDB deve ser armazenada em uma variável de ambiente, evitando expor credenciais diretamente no código-fonte.

Recomenda-se também:

- Não publicar credenciais ou strings de conexão no GitHub.
- Manter o arquivo `.env` fora do controle de versão, caso seja utilizado.
- Validar os dados recebidos nas requisições.
- Tratar erros relacionados ao banco de dados e aos identificadores inválidos.
- Implementar autenticação e autorização caso a API seja utilizada em um ambiente de produção.

## 👨‍💻 Autor

**Nicollas Cristante Gonçalves**

GitHub: [Cristantenicollas](https://github.com/Cristantenicollas)

Repositório: [api-produtos-naorelacional](https://github.com/Cristantenicollas/api-produtos-naorelacional)

---

Desenvolvido com Node.js, Express e MongoDB.
