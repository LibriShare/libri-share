# Primeiros Passos

Bem-vindo ao **LibriShare**! Este guia ajudar-te-á a configurar o ambiente e a realizar o teu primeiro acesso à plataforma.

## Acesso Rápido (Demo)
Se estiveres a utilizar a versão de demonstração online, basta acederes ao link fornecido e utilizares as credenciais de teste ou criares uma nova conta.

## Instalação Local (Para Desenvolvedores)

Se pretendes rodar o projeto na tua própria máquina, certifica-te de que tens o **Docker** instalado.

1.  **Clone o Repositório:**
    ```bash
    git clone [https://github.com/LibriShare/libri-share.git](https://github.com/LibriShare/libri-share.git)
    cd libri-share-back-end/backend
    ```

2.  **Inicie os Serviços:**
    Execute o comando para subir o Banco de Dados e a API:
    ```bash
    docker-compose up -d
    ```

3.  **Inicie o Front-end:**
    Navegue até à pasta do front-end e inicie o servidor:
    ```bash
    cd ../../libri-share-front-end/librishare
    pnpm install && pnpm dev
    ```
    Acede a `http://localhost:3000`.

## Primeiro Login

1.  Na tela inicial, clica em **"Criar Conta"** se ainda não tiveres registo.
2.  Preenche o teu **Nome**, **E-mail** e **Senha**.
3.  Após o login, serás redirecionado para o **Dashboard**, onde verás o resumo da tua atividade.