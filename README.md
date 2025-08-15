# Pizza Shop Server

Backend completo para gerenciamento de pedidos de uma pizzaria, fornecendo API REST para cadastro de clientes, cardápio, pedidos, autenticação e administração do sistema. Ideal para uso em conjunto com aplicações web/mobile como o `pizza-shop-client`.

---

## Principais funcionalidades e casos de uso

- Cadastro e autenticação de usuários (clientes e administradores)
- Gerenciamento de cardápio: pizzas, sabores, tamanhos, adicionais
- Cadastro e gerenciamento de pedidos
- Processamento de status do pedido (em preparação, em entrega, finalizado)
- Histórico de pedidos por usuário
- Rotas protegidas por autenticação e autorização
- Integração com sistemas de pagamento (mock ou real, conforme implementação)
- Área administrativa para controle de produtos, pedidos e usuários

---

## Stack e tecnologias utilizadas

- **Node.js**: Plataforma principal do backend
- **Express.js**: Framework para rotas e middlewares HTTP
- **Banco de Dados**: MongoDB ou PostgreSQL (ajustar conforme o projeto)
- **JWT**: Autenticação via tokens
- **dotenv**: Gerenciamento de variáveis de ambiente
- **Mongoose/Sequelize/Prisma**: ORM/ODM para o banco de dados (ajustar conforme o projeto)
- **Jest/Supertest**: Para testes automatizados (se aplicável)
- **Outros**: CORS, Helmet, Bcrypt, etc.

---

## Estrutura de pastas

```
pizza-shop-server/
├── src/
│   ├── config/         # Configurações gerais e conexão com o banco
│   ├── controllers/    # Lógica das rotas (ex: pedidos, auth, cardápio)
│   ├── middlewares/    # Middlewares de autenticação, erros, etc.
│   ├── models/         # Modelos do banco de dados (User, Pizza, Order, etc)
│   ├── routes/         # Definição das rotas da API
│   ├── services/       # Regras de negócio e integrações externas
│   ├── utils/          # Funções auxiliares
│   └── app.js          # Configuração principal do servidor
├── tests/              # Testes automatizados (unitários/integrados)
├── .env.example        # Exemplo de variáveis de ambiente
├── package.json        # Dependências e scripts do projeto
└── README.md           # Documentação do projeto
```

### Explicação das principais partes

- **src/config/**: Parâmetros do ambiente, conexão com banco, inicialização de serviços.
- **src/controllers/**: Implementação das regras de cada endpoint.
- **src/middlewares/**: Autenticação, tratamento de erros, validação, etc.
- **src/models/**: Schemas/tabelas do banco (Usuário, Pedido, Produto…).
- **src/routes/**: Arquivo de rotas agrupando endpoints por recurso.
- **src/services/**: Camada de negócio e integrações com APIs externas.
- **src/utils/**: Helpers para formatação, validação, etc.
- **tests/**: Scripts de teste automatizado.

---

## Instalação e execução local

### Pré-requisitos

- Node.js (18.x+ recomendado)
- npm ou yarn
- MongoDB ou PostgreSQL disponível (local ou remoto)

### Passo a passo

1. **Clone o repositório**
   ```bash
   git clone https://github.com/Cardosofiles/pizza-shop-server.git
   cd pizza-shop-server
   ```

2. **Configure as variáveis de ambiente**
   - Copie o arquivo `.env.example` para `.env` e informe as configurações necessárias (ex: URL do banco, JWT_SECRET, PORT).

3. **Instale as dependências**
   ```bash
   npm install
   # ou
   yarn
   ```

4. **(Se necessário) Execute migrações do banco**
   ```bash
   npm run migrate
   # ou
   yarn migrate
   ```

5. **Inicie o servidor**
   ```bash
   npm start
   # ou
   yarn start
   ```

6. **Acesse a API**
   - Por padrão em: [http://localhost:5000](http://localhost:5000)

---

## Como executar testes

```bash
npm test
# ou
yarn test
```

---

## Exemplos de uso dos endpoints

### Cadastro de usuário

```http
POST /api/auth/register
Content-Type: application/json

{
  "name": "Maria",
  "email": "maria@email.com",
  "password": "senhaSegura123"
}
```

### Obter cardápio de pizzas

```http
GET /api/menu
```

### Criar novo pedido

```http
POST /api/orders
Authorization: Bearer <token>
Content-Type: application/json

{
  "items": [
    {
      "pizzaId": "abc123",
      "size": "grande",
      "quantity": 2,
      "extras": ["catupiry"]
    }
  ],
  "address": "Rua das Pizzas, 100"
}
```

---

## Boas práticas e recomendações

- Utilize variáveis de ambiente para dados sensíveis e URLs.
- Proteja rotas críticas utilizando autenticação e autorização.
- Mantenha o código modularizado e organizado por domínio/feature.
- Escreva e mantenha testes para garantir a qualidade e evitar regressões.
- Atualize dependências e revise alertas de segurança periodicamente.
- Contribua seguindo padrões de branch, PR e código definidos no repositório.

---

*Para dúvidas, sugestões ou contribuições, abra uma issue ou pull request!*

## 📫 Contato

<div align="center">

<a href="mailto:cardosofiles@outlook.com">
  <img src="https://img.shields.io/badge/Email-0078D4?style=for-the-badge&logo=microsoftoutlook&logoColor=white" alt="Email"/>
</a>
<a href="https://www.linkedin.com/in/joaobatista-dev/" target="_blank">
  <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
</a>
<a href="https://github.com/Cardosofiles" target="_blank">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</a>
<a href="https://cardosofiles.dev/" target="_blank">
  <img src="https://img.shields.io/badge/Portfólio-222222?style=for-the-badge&logo=about.me&logoColor=white" alt="Portfólio"/>
</a>

</div>
