# Product Backlog - LibriShare

## 1. Introdução

Este documento representa o Product Backlog do projeto **LibriShare**. Ele serve como a fonte única da verdade para o desenvolvimento da plataforma, listando as funcionalidades desejadas, melhorias e correções necessárias para entregar valor aos leitores que desejam organizar suas bibliotecas pessoais e gerenciar empréstimos.

---

## 2. Épicos

Para organizar o desenvolvimento, as funcionalidades do LibriShare foram agrupadas em grandes corpos de trabalho, denominados Épicos:

- **Usuário & Perfil:** Funcionalidades de acesso, segurança e personalização da conta.
- **Biblioteca & Acervo:** Gestão do catálogo de livros e organização das estantes virtuais.
- **Leitura & Metas:** Acompanhamento do progresso de leitura e histórico.
- **Empréstimos:** Controle de livros emprestados a terceiros.
- **Comunidade (Social):** Interação com outros usuários.

---

## 3. Histórias de Usuário (User Stories)

Abaixo estão as histórias detalhadas, priorizadas e categorizadas por épico.

### 3.1 Épico: Usuário & Perfil

Foca na entrada do usuário na plataforma e na gestão de seus dados pessoais.

| ID | Eu, como usuário, gostaria de... | Para poder... | Status |
| :---: | -------------------------------- | ------------- | :---: |
| **US01** | Me cadastrar na plataforma usando nome, e-mail e senha | Ter minha própria biblioteca digital segura. | ✅ |
| **US02** | Fazer login com minhas credenciais | Acessar meus dados salvos de qualquer lugar. | ✅ |
| **US03** | Visualizar e editar meu perfil (Avatar, Bio) | Personalizar minha identidade na plataforma. | ✅ |
| **US04** | Excluir minha conta permanentemente | Ter controle total sobre meus dados e privacidade. | ✅ |
| **US05** | Fazer login utilizando minha conta Google | Acessar o sistema mais rápido sem decorar senhas. | ⏸️ |

### 3.2 Épico: Biblioteca & Acervo

O coração do sistema: adicionar, remover e organizar livros.

| ID | Eu, como usuário, gostaria de... | Para poder... | Status |
| :---: | -------------------------------- | ------------- | :---: |
| **US06** | Buscar livros em um catálogo online (OpenLibrary) | Adicionar livros à minha estante sem digitar tudo manualmente. | ✅ |
| **US07** | Cadastrar um livro manualmente | Inserir livros raros ou que não estão no catálogo online. | ✅ |
| **US08** | Classificar livros por status (Lendo, Lido, Para Ler) | Organizar minha fila de leitura e saber o que já terminei. | ✅ |
| **US09** | Criar uma Lista de Desejos (Wishlist) | Salvar livros que pretendo comprar futuramente. | ✅ |
| **US10** | Visualizar links de compra e preços na Wishlist | Facilitar a aquisição dos livros desejados. | ✅ |
| **US11** | Ver detalhes completos de um livro (Sinopse, Páginas, Autor) | Ter informações ricas sobre minha coleção. | ✅ |

### 3.3 Épico: Leitura & Metas

Funcionalidades para gamificação pessoal e rastreamento de hábitos.

| ID | Eu, como usuário, gostaria de... | Para poder... | Status |
| :---: | -------------------------------- | ------------- | :---: |
| **US12** | Definir uma meta anual de leitura | Me motivar a ler mais livros durante o ano. | ✅ |
| **US13** | Registrar o progresso de leitura (páginas lidas) | Saber quanto falta para terminar um livro. | ✅ |
| **US14** | Avaliar (estrelas) e resenhar livros lidos | Registrar minha opinião e lembrar se gostei da obra. | ✅ |
| **US15** | Visualizar meu histórico de atividades recentes | Relembrar minhas últimas interações na plataforma. | ✅ |
| **US16** | Reler um livro já concluído | Reiniciar a contagem de progresso sem perder o histórico antigo. | ✅ |

### 3.4 Épico: Empréstimos

Diferencial do LibriShare: gerenciar para quem você emprestou seus livros físicos.

| ID | Eu, como usuário, gostaria de... | Para poder... | Status |
| :---: | -------------------------------- | ------------- | :---: |
| **US17** | Registrar um empréstimo informando nome e data | Lembrar com quem está meu livro e quando ele deve voltar. | ✅ |
| **US18** | Visualizar lista de empréstimos ativos e atrasados | Ter controle rápido sobre itens pendentes. | ✅ |
| **US19** | Ser impedido de emprestar um livro que estou lendo | Evitar inconsistência de dados (não posso emprestar o que estou usando). | ✅ |
| **US20** | Enviar lembrete de cobrança por e-mail | Lembrar o amigo de devolver o livro de forma prática. |⏸️|
| **US21** | Dar baixa na devolução de um livro | Tornar o livro disponível novamente na minha estante. | ✅ |

### 3.5 Épico: Comunidade (Futuro)

*Além de poder gerenciar a sua biblioteca, o LibriShare terá uma rede social interna, podendo pegar emprestado livros de novos amigos criados na plataforma.*

| ID | Eu, como usuário, gostaria de... | Para poder... | Status |
| :---: | -------------------------------- | ------------- | :---: |
| **US22** | Seguir amigos na plataforma | Ver o que eles estão lendo. | ⏸️ |
| **US23** | Comentar nas atualizações de leitura de amigos | Interagir e discutir sobre livros. | ⏸️ |
| **US24** | Ver um feed de atividades da comunidade | Descobrir novos livros baseados no gosto de outros. | ⏸️ |
| **US25** | Solicitar empréstimo em bibliotecas de amigos | Ler um livro emprestado de um amigo. | ⏸️ |

---

## 4. Legenda de Status

- ✅ **Concluído:** Funcionalidade implementada, testada e em produção.
- 🚧 **Em Desenvolvimento:** Funcionalidade parcialmente implementada ou em testes.
- ⏸️ **Backlog/Futuro:** Mapeada mas não priorizada para o MVP atual.

---