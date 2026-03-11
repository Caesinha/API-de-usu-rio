# API de Usuários (Node.js)

Projeto **didático** de API REST de usuários usando **Node.js + Express**.

Serve como base para aprender a criar um backend simples e testar operações CRUD usando requisições HTTP.

---

## ✅ Requisitos

- Node.js instalado (versão 16+ recomendada)
- Terminal: PowerShell, cmd, Git Bash ou WSL

---

## 🚀 Como rodar

1) Abra o terminal na pasta do projeto (ou navegue até ela):

```bash
cd path/to/your/project/"API de Usuários (Node.js)"
```

> Dica: se você já estiver dentro da pasta, não precisa rodar esse comando.

2) Instale as dependências:

```bash
npm install
```

3) Inicie o servidor:

```bash
npm run dev
```

O servidor iniciará em **http://localhost:3000** e ficará aguardando requisições.

---

## 🔌 Por que manter o terminal aberto?

O comando `npm run dev` inicia o servidor e mantém o processo em execução para responder às requisições.

- Se você **fechar o terminal**, o servidor para e as rotas deixam de funcionar.
- Para testar, utilize outro terminal ou outra ferramenta (Postman, Insomnia, etc.) enquanto o servidor estiver rodando.

---

## 📦 Endpoints (CRUD)

### ✅ Status da API
- `GET /` - retorna um JSON com os endpoints disponíveis

### ✅ Listar usuários
- `GET /users` - retorna uma lista de usuários

### ✅ Buscar usuário por ID
- `GET /users/:id` - busca um usuário pelo `id`

### ✅ Criar usuário
- `POST /users` - cria um usuário
- Body JSON:
  ```json
  { "name": "Fulano", "email": "fulano@example.com" }
  ```

### ✅ Atualizar usuário
- `PUT /users/:id` - atualiza os dados do usuário
- Body JSON:
  ```json
  { "name": "Novo Nome", "email": "novo@example.com" }
  ```

### ✅ Deletar usuário
- `DELETE /users/:id` - remove o usuário

---

## 📝 Observações importantes

- Os dados são mantidos **em memória** (não há banco de dados). Ao reiniciar o servidor, os dados retornam ao estado inicial.
- Este projeto é focado em aprendizagem; não é recomendado usá-lo em produção sem adicionar persistência, validação avançada e segurança.

---

## 🪟 Testando no PowerShell (Windows)

No PowerShell, o `curl` é um alias para `Invoke-WebRequest`, por isso o comando padrão falha em alguns casos.

### ✅ Usando o `curl.exe` (recomendado quando disponível)

```powershell
curl.exe -X POST http://localhost:3000/users \
  -H "Content-Type: application/json" \
  -d "{\"name\":\"Fulano\",\"email\":\"fulano@example.com\"}"
```

### ✅ Usando o cmdlet do PowerShell (`Invoke-RestMethod`)

```powershell
Invoke-RestMethod -Method Post -Uri http://localhost:3000/users \
  -Headers @{ "Content-Type" = "application/json" } \
  -Body '{ "name": "Fulano", "email": "fulano@example.com" }'
```

---

## 🐧 Testando no Git Bash / WSL (Linux-like)

No Git Bash (ou WSL), o `curl` funciona como no Linux:

```bash
curl -X POST http://localhost:3000/users \
  -H "Content-Type: application/json" \
  -d '{"name":"Fulano","email":"fulano@example.com"}'
```

---

## 🧠 Próximos passos (opcional)

Se quiser evoluir este projeto, você pode adicionar:

- Banco de dados (SQLite, MongoDB, PostgreSQL)
- Autenticação (JWT)
- Validação de esquema (Joi, Zod)
- Camadas (routes/controllers/models)
- Testes automatizados (Jest + Supertest)
