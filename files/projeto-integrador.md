# Projeto Integrador

## Objetivo Geral
Desenvolver um sistema mobile completo e integrado, conectando **Banco de Dados Relacional**, **API RESTful (Backend)** e **Aplicativo Móvel (Frontend)**. O projeto simula o ciclo real de desenvolvimento de software, desde a modelagem de dados até a interface do usuário.

---

## Requisitos Técnicos

### 1. Documentação Obrigatória (README.md)
O repositório do projeto deve obrigatoriamente conter um arquivo `README.md` na raiz com a seguinte estrutura:
* **Título do Projeto:** Nome da aplicação desenvolvida pela equipe.
* **Objetivo Geral:** Descrição clara do propósito principal do sistema.
* **Objetivos Específicos:** Lista detalhada das metas técnicas e funcionais do projeto.
* **Modelagem de Dados:**
  * Imagem do Modelo Entidade-Relacionamento (DER).
  * Imagem do Modelo Lógico.

### 2. Banco de Dados e Migrations
* **Modelagem:** Entregar o Modelo Entidade-Relacionamento (DER) e o Esquema Lógico detalhado (PKs, FKs e tipos de dados).
* **Migrations em JS:** Os scripts de banco de dados devem ser compostos por dois arquivos `.js` obrigatoriamente localizados na pasta `scripts/`:
  * `scripts/create-db.js`: Importa a conexão (`src/database/conn.js`), conecta ao SGBD e executa a criação do banco de dados e suas tabelas.
  * `scripts/insert-db.js`: Importa a conexão (`src/database/conn.js`), conecta ao banco e executa a inserção dos dados iniciais.
* **Configuração de Scripts (`package.json`):** O arquivo `package.json` do backend deve conter obrigatoriamente a seguinte estrutura na propriedade `"scripts"`:

```json
"scripts": {
  "start": "node .",
  "dev": "nodemon .",
  "db:create": "node scripts/create-db.js",
  "db:insert": "node scripts/insert-db.js"
}
```

### 3. Programação Backend (Node.js + Express)
* **Estrutura de Pastas Obrigatória:**
```
  src/
  ├── controllers/
  ├── services/
  ├── database/
  ├── validators/
  ├── routes/
  ├── middlewares/
  ├── utils/
  ├── assets/
  └── app.js
  ```
* **Regras & Conexão:** Todas as rotas (CRUD) devem acessar o banco de dados via `services` e `controllers`.
* **Validação:** Tratamento rigoroso de requisições de entrada utilizando `express-validator`.
* **Middlewares:** Aplicação de middlewares para autenticação, autorização, tratamento de erros, validações ou regras gerais.

### 4. Programação Frontend Mobile (React Native)
* **Estrutura de Pastas Obrigatória:**
```
  src/
  ├── components/
  ├── screens/
  ├── services/
  ├── hooks/
  ├── utils/
  ├── styles/
  ├── assets/
  └── App.js
```
* **Navegação & UI:** Fluxo de navegação com `react-navigation` e elementos visuais baseados na biblioteca `react-native-paper`.
* **Design System:** Camada de abstração para padronização visual (cores, fontes, espaçamentos e componentes base).
* **Validação:** Validação dos formulários utilizando a biblioteca `Yup`.
* **Consumo de API:** Comunicação com a API REST através da camada de `services` (ex: Axios ou Fetch).

---

## Listas de Tarefas por Eixo

### 1. Banco de Dados e Documentação

| Título da Tarefa | Descrição | Realizado |
| :--- | :--- | :---: |
| **1.1. Elaboração da Modelagem** | Criar o Diagrama Entidade-Relacionamento (DER) e o Modelo Lógico com PKs e FKs. |  |
| **1.2. Documentação no README.md** | Redigir o arquivo README.md contendo Título, Objetivo Geral, Objetivos Específicos e imagens dos modelos DER/Lógico. |  |
| **1.3. Conexão com Banco de Dados** | Configurar a conexão com o SGBD usando o driver `mysql2` na pasta `src/database/`. |  |
| **1.4. Scripts de Migration em JS** | Desenvolver os scripts `scripts/create-db.js` (criação da estrutura) e `scripts/insert-db.js` (povoamento de dados). |  |

---

### 2. Programação Backend (Node.js + Express)

| Título da Tarefa | Descrição | Realizado |
| :--- | :--- | :---: |
| **2.1. Configuração do package.json** | Configurar os comandos `"start"`, `"dev"`, `"db:create"` e `"db:insert"` no bloco `"scripts"` do `package.json`. |  |
| **2.2. Estrutura de Pastas do Backend** | Criar a estrutura com as pastas `controllers`, `services`, `database`, `validators`, `routes`, `middlewares` e o arquivo `app.js`. |  |
| **2.3. Validação e Middlewares Backend** | Configurar sanitização de dados com `express-validator` e middlewares de tratamento de erros/autenticação. |  |
| **2.4. Desenvolvimento de Endpoints (CRUD)** | Implementar as rotas integrando os controladores (`controllers`) e regras de negócio (`services`) ao banco via `mysql2`. |  |

---

### 3. Programação Mobile (React Native)

| Título da Tarefa | Descrição | Realizado |
| :--- | :--- | :---: |
| **3.1. Estrutura de Pastas do Mobile** | Organizar a arquitetura do projeto React Native nas pastas: `components`, `screens`, `services`, `hooks`, `utils`, `styles` e `assets`. |  |
| **3.2. Design System & Estilização** | Criar a camada de abstração para os tokens de estilo e padronizar componentes base com `react-native-paper`. |  |
| **3.3. Configuração de Navegação** | Estruturar o fluxo de navegação entre as telas da aplicação utilizando `react-navigation`. |  |
| **3.4. Validação de Formulários Mobile** | Integrar o esquema de validação do `Yup` aos formulários das telas. |  |
| **3.5. Integração com a API Backend** | Configurar as requisições HTTP para a API REST na camada `src/services/` (utilizando Axios ou Fetch). |  |
| **3.6. Teste de Fluxo End-to-End** | Validar o ciclo completo funcional: formulário mobile $\rightarrow$ envio à API $\rightarrow$ validação backend $\rightarrow$ persistência no banco. |  |

## Tecnologias Utilizadas

| Título | Descrição | Link |
| :--- | :--- | :--- |
| **Node.js** | Ambiente de execução JavaScript no lado do servidor para construção de aplicações escaláveis. | https://nodejs.org/ |
| **Express** | Framework web minimalista e flexível para Node.js para criação de rotas e APIs RESTful. | https://expressjs.com/ |
| **MySQL** | Sistema de Gerenciamento de Banco de Dados Relacional (SGBD) para persistência de dados. | https://www.mysql.com/ |
| **mysql2** | Driver do MySQL para Node.js com foco em performance e suporte a *Prepared Statements*. | https://github.com/sidorares/node-mysql2 |
| **express-validator** | Conjunto de middlewares para validação e sanitização de requisições HTTP no Express. | https://express-validator.github.io/docs/ |
| **React Native** | Framework para desenvolvimento de aplicações móveis nativas usando React e JavaScript. | https://reactnative.dev/ |
| **React Navigation** | Biblioteca para gerenciamento de roteamento e navegação em aplicativos React Native. | https://reactnavigation.org/ |
| **React Native Paper** | Biblioteca de componentes visuais baseada nas diretrizes do Material Design. | https://reactnativepaper.com/ |
| **Yup** | Construtor de esquemas baseados em objetos para validação de dados e formulários. | https://github.com/jquense/yup |

---
