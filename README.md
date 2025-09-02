# 🏋️‍♂️ GymPass Style API

API de uma aplicação no estilo **GymPass** desenvolvida em **Node.js**, utilizando **TypeScript**, **Fastify** e **Prisma**, seguindo os princípios **SOLID** para garantir um código **limpo, escalável e de fácil manutenção**.  

---

## 🚀 Tecnologias Utilizadas

- **Node.js** – Ambiente de execução JavaScript no servidor.  
- **TypeScript** – Superset do JavaScript com tipagem estática.  
- **Fastify** – Framework web rápido e minimalista.  
- **Prisma** – ORM para comunicação com o banco de dados (**PostgreSQL**).  
- **Zod** – Validação de esquemas e tipos.  
- **Vitest** – Framework de testes para Node.js e Vite.  
- **Docker** – Containerização para ambiente de desenvolvimento com PostgreSQL.  
- **TSX** – Execução de arquivos TypeScript sem build prévio (dev).  
- **TSUP** – Bundler para gerar builds otimizadas em TypeScript.  

---

## 📋 Funcionalidades

### 👤 Usuários
- Cadastro de usuários.  
- Autenticação via **JWT**.  
- Visualização do perfil.  
- Histórico de check-ins.  
- Contagem de check-ins realizados.  

### 🏢 Academias
- Cadastro de academias (**somente administradores**).  
- Busca por **nome**.  
- Busca por **proximidade** (até 10 km).  

### ✅ Check-ins
- Realizar check-in em academias.  
- Validação de check-in (**apenas administradores**).  
- Regras de negócio aplicadas:
  - Máx. 1 check-in por dia.  
  - Distância máxima de 100m da academia.  
  - Validação somente até 20 minutos após a criação.  

---

## 📜 Requisitos Funcionais (RFs)
- [x] Cadastro de usuários  
- [x] Autenticação  
- [x] Perfil do usuário logado  
- [x] Contagem de check-ins  
- [x] Histórico de check-ins  
- [x] Buscar academias próximas  
- [x] Buscar academias pelo nome  
- [x] Realizar check-in  
- [x] Validar check-in  
- [x] Cadastrar academia  

---

## 🧩 Regras de Negócio (RNs)
- ❌ Cadastro com e-mail duplicado não permitido.  
- ❌ Máx. 1 check-in por dia.  
- ❌ Check-in apenas até **100m de distância**.  
- ⏱️ Check-in validado até 20 minutos após criação.  
- 🔑 Validação e cadastro de academias somente por **administradores**.  

---

## ⚙️ Requisitos Não-Funcionais (RNFs)
- 🔒 Senhas criptografadas.  
- 🗄️ Persistência em banco **PostgreSQL**.  
- 📑 Paginação de 20 itens por página.  
- 🔑 Autenticação via **JWT**.  

---

## 🛠️ Como Rodar o Projeto

### Pré-requisitos
- **Node.js** >= 18  
- **Docker** e **Docker Compose**  
- **PostgreSQL**  

### Passos
```bash
# Clone o repositório
git clone https://github.com/henrylsilveira/03-api-solid.git

# Entre na pasta do projeto
cd gympass-style-api

# Instale as dependências
npm install

# Suba o container do banco
docker-compose up -d

# Rode as migrations
npx prisma migrate dev

# Execute o projeto em modo desenvolvimento
npm run dev

