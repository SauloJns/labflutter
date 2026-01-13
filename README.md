<img width="150" height="150" alt="Tehokas Logo" src="https://github.com/user-attachments/assets/459d9cc4-ad45-46bb-a1f4-0687ad9e6924" />
# Tehokas Checklist

O **Tehokas Checklist** é um sistema web para gerenciamento de projetos e tarefas, com foco em organização, produtividade e visualização clara do andamento dos projetos.

O sistema permite criar projetos, gerenciar tarefas em formato **Kanban** e acompanhar o status geral por meio de indicadores visuais simples. Este projeto foi desenvolvido como MVP para o desafio técnico da vaga de Estágio Full Stack na Tehokas, com o objetivo de demonstrar integração entre frontend e backend, organização de código e domínio do fluxo de uma aplicação web completa.

## Tecnologias Utilizadas

### Backend
* **Laravel 10**
* **PHP 8.1+**
* **Autenticação:** Laravel Breeze
* **Banco de Dados:** SQLite (automático para desenvolvimento)

### Frontend
* **React 18**
* **Inertia.js**
* **Tailwind CSS**

---

## Instalação e Execução Local

### Pré-requisitos

Certifique-se de ter as seguintes ferramentas instaladas em sua máquina:
* **PHP 8.1** ou superior
* **Composer**
* **Node.js 18** ou superior
* **Git**

### Passo a Passo

#### 1. Clonar o repositório
```bash
git clone [https://github.com/seu-usuario/tehokas-checklist.git](https://github.com/seu-usuario/tehokas-checklist.git)
cd tehokas-checklist
```

#### 2. Instalar dependências
Acesse a pasta do backend e instale as dependências do PHP e do Node:

```bash
cd backend
composer install
npm install
```

#### 3. Configurar ambiente
Copie o arquivo de exemplo e gere a chave da aplicação:

```bash
cp .env.example .env
php artisan key:generate
```

#### 4. Configurar Banco de Dados (SQLite)
Crie o arquivo do banco de dados:

```bash
touch database/database.sqlite
```

> **Atenção:** No arquivo `.env`, certifique-se de que a conexão com o banco esteja configurada com o caminho absoluto:
>
> `DB_CONNECTION=sqlite`
> `DB_DATABASE=/caminho/absoluto/para/tehokas-checklist/backend/database/database.sqlite`

#### 5. Executar migrações
```bash
php artisan migrate
```

---

## Inicializando a Aplicação

#### Terminal 1: Frontend
Compile os assets em tempo real:
```bash
npm run dev
```

#### Terminal 2: Backend
Inicie o servidor local do Laravel:
```bash
php artisan serve
```

Acesse a aplicação em seu navegador através da URL:
**http://localhost:8000**

---

## Sobre o Desafio Técnico

O principal desafio técnico do projeto foi a implementação do quadro **Kanban**, garantindo uma boa experiência de uso sem comprometer a consistência dos dados.

### Pontos de atenção:
* Atualização imediata da interface ao mover tarefas.
* Persistência correta do status no backend.
* Tratamento de erros para evitar inconsistências visuais.

### Solução adotada:
* Utilização dos eventos nativos de **drag-and-drop** do HTML5.
* Requisição assíncrona para atualizar o status da tarefa no backend.
* **Rollback visual** automático em caso de falha na requisição.
* Uso do **Inertia.js** para preservar o estado da página e evitar recarregamentos desnecessários.
