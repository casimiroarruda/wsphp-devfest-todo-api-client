# 🚀 Cliente Web - Workshop "PHP do Jeito Certo"

Este é o **cliente frontend** desenvolvido para o workshop "PHP do Jeito Certo" no **DevFest Pernambuco**.

Ele é uma aplicação web moderna, construída com **Nuxt 4** (Vue.js) e estilizada com **TailwindCSS**, desenhada para simular uma interface real (inspirada no Google Tasks).

🎯 **O objetivo deste projeto é servir como uma ferramenta de teste para a API em PHP que você construirá durante o workshop.**

---

## 📋 Pré-requisitos

Para rodar este projeto, você precisa ter instalado em sua máquina:

* **[Node.js](https://nodejs.org/)** (Versão LTS recomendada, v18 ou superior)
* **[pnpm](https://pnpm.io/pt/installation)** (Gerenciador de pacotes rápido e eficiente)
* **Git**

---

## 🛠️ Instalação e Configuração

Siga os passos abaixo no seu terminal para preparar o ambiente do cliente.

### 1. Clonar o Repositório

```bash
git clone [https://github.com/casimiroarruda/wsphp-devfest-todo-api-client.git](https://github.com/casimiroarruda/wsphp-devfest-todo-api-client.git)
cd wsphp-devfest-todo-api-client
```

Com certeza! Facilita muito baixar o arquivo direto.

Aqui está o README.md prontinho para você colocar na pasta do seu projeto cliente:

README.md

Markdown

# 🚀 Cliente Web - Workshop "PHP do Jeito Certo"

Este é o **cliente frontend** desenvolvido para o workshop "PHP do Jeito Certo" no **DevFest Pernambuco**.

Ele é uma aplicação web moderna, construída com **Nuxt 4** (Vue.js) e estilizada com **TailwindCSS**, desenhada para simular uma interface real (inspirada no Google Tasks).

🎯 **O objetivo deste projeto é servir como uma ferramenta de teste para a API em PHP que você construirá durante o workshop.**

---

## 📋 Pré-requisitos

Para rodar este projeto, você precisa ter instalado em sua máquina:

* **[Node.js](https://nodejs.org/)** (Versão LTS recomendada, v18 ou superior)
* **[pnpm](https://pnpm.io/pt/installation)** (Gerenciador de pacotes rápido e eficiente)
* **Git**

---

## 🛠️ Instalação e Configuração

Siga os passos abaixo no seu terminal para preparar o ambiente do cliente.

### 1. Clonar o Repositório

```bash
git clone [https://github.com/casimiroarruda/wsphp-devfest-todo-api-client.git](https://github.com/casimiroarruda/wsphp-devfest-todo-api-client.git)
cd wsphp-devfest-todo-api-client
```

### 2. Instalar Dependências

Utilize o pnpm para baixar as bibliotecas necessárias.

```bash
pnpm install
```

### 3. Configurar Variáveis de Ambiente
Este cliente precisa saber onde sua API PHP estará rodando. Usamos um arquivo .env para isso.
Crie um arquivo .env na raiz do projeto baseando-se no exemplo fornecido:
```bash
cp .env.example .env
```
Abra o arquivo .env recém-criado e verifique o conteúdo. Ele deve se parecer com isso:

```dotenv
# .env
# Define a URL onde o cliente buscará os dados.
# Durante o workshop, sua API PHP deverá rodar nesta porta (8000).
NUXT_PUBLIC_API_URL="http://localhost:8000"
```
Nota: Se você decidir rodar seu servidor PHP em uma porta diferente de 8000, lembre-se de alterar este arquivo.

## ▶️ Rodando o Cliente
Com tudo configurado, inicie o servidor de desenvolvimento do frontend:

```Bash
pnpm dev
```
Após alguns segundos, você verá uma mensagem indicando que o servidor está pronto.

👉 Abra no seu navegador: http://localhost:3000

## 🔗 Conectando à sua API PHP
Ao abrir o cliente no navegador, é normal que você veja uma mensagem de erro inicialmente (ou uma lista vazia que não adiciona tarefas).

Isso acontece porque sua API PHP ainda não está rodando!

Para que tudo funcione, você precisará (em outro terminal) iniciar o seu servidor PHP na porta definida no .env.

Exemplo do comando que usaremos no workshop para rodar o PHP:

```Bash
# (No diretório do seu projeto PHP)
php -S localhost:8000 index.php
```
Assim que sua API PHP estiver rodando e configurada corretamente (incluindo os cabeçalhos de CORS que veremos), o cliente web se conectará automaticamente e começará a funcionar.

## ❓ Solução de Problemas Comuns

* Erro `"Failed to fetch"` ou similar:
    1. Verifique se o servidor PHP está rodando.
    2. Verifique se o PHP está rodando na mesma porta definida no .env deste projeto (padrão: 8000).
* Erro de CORS no console do navegador:
    * Isso significa que sua API PHP está rodando, mas não enviou os cabeçalhos de permissão necessários para o frontend se comunicar com ela. Isso será coberto no Bloco 1 do workshop.
---
Made with 💜 for DevFest Pernambuco.
