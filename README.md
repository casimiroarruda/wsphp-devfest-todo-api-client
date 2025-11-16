# 🚀 Cliente da API To-Do em PHP (php-todo-api-client)

Este é o projeto frontend (cliente web) desenvolvido para o workshop de introdução ao PHP Moderno. Ele utiliza **Nuxt 4** e **TailwindCSS** para criar uma interface limpa, similar ao Google Tasks, e é projetado para consumir a API To-Do que será construída em PHP.

## ✨ Visão Geral

O objetivo deste cliente é fornecer uma interface de usuário (UI) funcional para que os participantes do workshop possam testar a API PHP que estão construindo. Ele se conectará ao backend PHP local para listar, criar, e (opcionalmente) atualizar e deletar tarefas.

## 🛠️ Tecnologias Utilizadas

* **[Nuxt 4](https://nuxt.com/)**: O framework frontend (baseado em Vue 3).
* **[pnpm](https://pnpm.io/)**: O gerenciador de pacotes.
* **[TailwindCSS](https://tailwindcss.com/)**: Para estilização utility-first.
* **[@nuxt/icon](https://github.com/nuxt-modules/icon)**: Para ícones SVG fáceis de usar.

---

## 🚀 Rodando o Projeto Localmente

Siga estes passos para executar o cliente frontend em sua máquina.

### Pré-requisitos

Antes de começar, garanta que você tenha os seguintes softwares instalados:
* [Node.js](https://nodejs.org/) (versão 18 ou superior)
* [pnpm](https://pnpm.io/installation) (Gerenciador de pacotes)

### Passos

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/SEU-USUARIO/php-todo-api-client.git](https://github.com/SEU-USUARIO/php-todo-api-client.git)
    cd php-todo-api-client
    ```
    *(Lembre-se de alterar `SEU-USUARIO` para o seu nome de usuário/organização no GitHub)*

2.  **Instale as dependências:**
    ```bash
    pnpm install
    ```

3.  **Configure o arquivo de ambiente (.env):**
    Este projeto precisa saber onde a sua API PHP está rodando. Copie o arquivo de exemplo para criar sua configuração local:

    ```bash
    cp .env.example .env
    ```

    Agora, abra o arquivo `.env` e confirme que a `NUXT_PUBLIC_API_URL` aponta para o local onde sua API PHP estará rodando. O padrão do workshop é `http://localhost:8000`.

    ```env
    # .env
    # Esta porta (8000) deve ser a mesma onde você
    # rodará o servidor PHP (ex: php -S localhost:8000)
    NUXT_PUBLIC_API_URL="http://localhost:8000"
    ```

4.  **Inicie o servidor de desenvolvimento:**
    ```bash
    pnpm dev
    ```

5.  **Pronto!**
    Abra seu navegador e acesse [http://localhost:3000](http://localhost:3000). Você verá a interface do cliente To-Do.

---

## 🔗 Conectando com o Backend

Este cliente **não** funcionará corretamente a menos que a API PHP esteja rodando simultaneamente.

Certifique-se de que, em outro terminal, você esteja executando o servidor PHP (do projeto backend) na porta definida no seu arquivo `.env` (ex: `localhost:8000`).

➡️ **Link para o repositório da API PHP:** `[COLOQUE AQUI A URL DO SEU REPOSITÓRIO BACKEND]`