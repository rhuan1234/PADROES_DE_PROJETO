
# Padrões de Projeto

Um projeto Node.js com TypeScript que demonstra a aplicação de padrões de projeto em uma API REST.

## Descrição

Este projeto é uma API REST construída com **Express** e **TypeScript** que implementa diversos padrões de projeto, como Factory, Decorator, Adapter e Composite. O projeto utiliza **MongoDB** como banco de dados e está containerizado com **Docker**.

## Requisitos

- **Node.js**: >= 20.0.0
- **Docker** e **Docker Compose** (opcional, apenas se quiser rodar MongoDB via container)
- **npm** ou **yarn**

## Como Rodar o Projeto

### 1. Clone o repositório

```bash
git clone https://github.com/rhuan1234/PADROES_DE_PROJETO
cd PADROES_DE_PROJETO
```

### 2. Instale as dependências

```bash
npm install
```

### 3. Configure as variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto com as configurações necessárias:

```env
MONGODB_URI=mongodb://localhost:27017
PORT=3000
```

### 4. Inicie o MongoDB

**Opção A: Com Docker Compose**

```bash
docker-compose up -d
```

Isso iniciará o MongoDB na porta `27017`.

**Opção B: MongoDB Local**

Certifique-se de ter o MongoDB instalado e rodando localmente.

### 5. Inicie o servidor de desenvolvimento

```bash
npm start
```

O servidor estará disponível em `http://localhost:3000`.

O comando `npm start` executa o TypeScript em modo watch, recompilando automaticamente quando houver mudanças.

## Estrutura do Projeto

```
src/
├── adapters/              # Adaptadores e configuração de entrada
│   ├── controllers/       # Controllers das rotas
│   ├── decorators/        # Decoradores (ex: logging)
│   ├── factories/         # Padrão Factory para criar instâncias
│   ├── presentations/     # Configuração da API (Express)
│   └── validations/       # Validações de dados
├── dataSources/           # Camada de acesso a dados
│   ├── config/           # Configuração do MongoDB
│   └── db/               # Implementação de repositórios
├── entities/              # Entidades do domínio
├── usecases/              # Casos de uso da aplicação
└── index.ts              # Ponto de entrada
```

## Padrões Implementados

- **Factory Pattern**: Criação de instâncias complexas de controllers e validações
- **Decorator Pattern**: Adição de comportamentos (logging) sem modificar a classe original
- **Adapter Pattern**: Adaptação do Express para a camada de aplicação
- **Composite Pattern**: Composição de validações múltiplas
- **Repository Pattern**: Abstração da camada de dados

## Funcionalidades

- ✅ Criar tarefas (POST /tasks)
- ✅ Deletar tarefas (DELETE /tasks/:id)
- ✅ Validação de dados com Composite Pattern
- ✅ Logging automático de erros
- ✅ CORS habilitado

## Tecnologias Utilizadas

- **Node.js** com **TypeScript**
- **Express** - Framework web
- **MongoDB** - Banco de dados
- **Validator** - Validação de dados
- **Docker** - Containerização
- **ESLint** - Linter
- **tsc-watch** - Compilador TypeScript em modo watch

## Scripts Disponíveis

- `npm start` - Inicia o servidor em modo desenvolvimento com auto-reload
