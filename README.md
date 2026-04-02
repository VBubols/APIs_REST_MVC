# 🏥 APIs REST MVC

> Exercícios progressivos de construção de APIs com **Express** e arquitetura **MVC** — sem banco de dados, só JavaScript puro e arrays em memória.

---

## 📁 Estrutura do Repositório

```
APIs_REST_MVC/
├── API_CLINICA/          # API completa de agendamentos
│   ├── DB/               # Arrays em memória (fonte de dados)
│   ├── src/
│   │   ├── models/       # Manipulação dos dados
│   │   └── controllers/  # Lógica das requisições
│   └── app.js            # Rotas e servidor
└── exercicios_Express/   # Exercícios base com Express
```

---

## 🩺 API Clínica

API REST de agendamentos para uma clínica fictícia. Gerencia **pacientes**, **médicos** e **consultas** com arquitetura MVC.

### Entidades

| Entidade | Campos |
|----------|--------|
| Paciente | `id`, `nome`, `telefone` |
| Médico   | `id`, `nome`, `especialidade` |
| Consulta | `id`, `pacienteId`, `medicoId`, `data`, `status` |

---

### 🛣️ Rotas

#### Pacientes

| Método | Rota | Descrição |
|--------|------|-----------|
| `GET` | `/pacientes` | Lista todos os pacientes |
| `POST` | `/pacientes` | Cadastra novo paciente (`nome` obrigatório) |

#### Médicos

| Método | Rota | Descrição |
|--------|------|-----------|
| `GET` | `/medicos` | Lista todos os médicos |
| `GET` | `/medicos?especialidade=cardiologia` | Filtra por especialidade |

#### Consultas

| Método | Rota | Descrição |
|--------|------|-----------|
| `GET` | `/consultas` | Lista consultas com nome do paciente e médico embutidos |
| `POST` | `/consultas` | Agenda nova consulta |
| `DELETE` | `/consultas/:id` | Cancela uma consulta |

---

### ⚠️ Regras de Negócio

- Ao criar uma consulta, `pacienteId` e `medicoId` são validados — retorna `404` se não existirem
- O `status` inicial de toda consulta é definido automaticamente como `"agendada"` pelo controller
- O `GET /consultas` retorna o `nome` do paciente e do médico embutidos em cada consulta

---

### ▶️ Como rodar

```bash
# Entre na pasta da API
cd API_CLINICA

# Instale as dependências
npm install

# Inicie o servidor
node app.js
```

---

### 🔧 Tecnologias

- [Node.js](https://nodejs.org/)
- [Express](https://expressjs.com/)
- ES Modules (`import/export`)
- Arrays em memória (sem banco de dados)

---

## 📚 Conceitos praticados

- Arquitetura **MVC** (Model · Controller)
- Rotas REST com Express
- Validação de dados no Controller
- Separação de responsabilidades entre camadas
- `Array.find`, `Array.map`, `Array.splice` para manipulação de dados
- Query params (`req.query`) e route params (`req.params`)

---

> Desenvolvido como exercício prático de back-end com Node.js e Express.
