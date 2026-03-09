# 🏥 API de Cadastro — Médicos e Dentistas Voluntários

API REST desenvolvida com **Node.js** e **Express** para cadastro de profissionais voluntários (médicos e dentistas) que desejam participar de ações sociais de saúde.

---

## 🚀 Tecnologias Utilizadas

- [Node.js](https://nodejs.org/)
- [Express](https://expressjs.com/)
- [dotenv](https://www.npmjs.com/package/dotenv)
- [Nodemon](https://nodemon.io/) *(ambiente de desenvolvimento)*

---

## 📁 Estrutura do Projeto

```
project-api/
├── server.js        # Arquivo principal da aplicação
├── .env             # Variáveis de ambiente
├── .gitignore       # Arquivos ignorados pelo Git
├── package.json     # Dependências e scripts
└── README.md        # Documentação do projeto
```

---

## ⚙️ Como Executar o Projeto

### Pré-requisitos

- Node.js instalado
- npm instalado

### Instalação

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/project-api.git

# Acesse a pasta do projeto
cd project-api

# Instale as dependências
npm install
```

### Variáveis de Ambiente

Crie um arquivo `.env` na raiz do projeto com o seguinte conteúdo:

```env
PORT=3000
```

### Rodando o servidor

```bash
npm run dev
```

O servidor estará disponível em: `http://localhost:3000`

---

## 📌 Rotas da API

### `GET /cadastros`
Retorna todos os profissionais cadastrados.

**Resposta de exemplo:**
```json
[
  {
    "id": 1,
    "nome": "João Silva",
    "email": "joao@email.com",
    "telefone": "11999998888",
    "mensagem": "Quero ser voluntário"
  }
]
```

---

### `POST /cadastros`
Cadastra um novo profissional voluntário.

**Body (JSON):**
```json
{
  "nome": "João Silva",
  "email": "joao@email.com",
  "telefone": "11999998888",
  "mensagem": "Quero ser voluntário"
}
```

**Resposta de sucesso (201):**
```json
{
  "message": "Cadastro criado com sucesso",
  "cadastro": {
    "id": 1,
    "nome": "João Silva",
    "email": "joao@email.com",
    "telefone": "11999998888",
    "mensagem": "Quero ser voluntário"
  }
}
```

---

## ✅ Validações

| Campo      | Regra                                      |
|------------|--------------------------------------------|
| `nome`     | Obrigatório, mínimo de 3 caracteres        |
| `email`    | Obrigatório, deve ser um e-mail válido     |
| `telefone` | Obrigatório, deve ter 10 ou 11 dígitos     |
| `mensagem` | Opcional, máximo de 500 caracteres         |

Em caso de erro de validação, a API retorna status `400` com a mensagem correspondente.

---

## 🗃️ Armazenamento

Os dados são armazenados **em memória** utilizando um array JavaScript. As informações são perdidas ao reiniciar o servidor.

---

## 🧪 Testando com Postman

1. Abra o Postman
2. Crie uma requisição `GET` para `http://localhost:3000/cadastros`
3. Crie uma requisição `POST` para `http://localhost:3000/cadastros` com o body em JSON

---

## 👨‍💻 Autor

Desenvolvido por **Lucas Couto Duarte**.
