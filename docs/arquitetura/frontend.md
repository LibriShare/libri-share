# Arquitetura do Frontend

O Frontend do LibriShare é uma *Single Page Application* (SPA) moderna, focada em performance e experiência do usuário (UX). A interface foi construída para ser responsiva, acessível e visualmente agradável, utilizando o modo escuro como padrão.

---

## 🎨 Prototipação e Design (v0.dev)

A concepção visual e a estrutura inicial dos componentes foram desenvolvidas utilizando a plataforma de IA generativa **v0.dev**.

Essa abordagem permitiu uma iteração rápida entre a ideia e o código (React/Tailwind), gerando uma base sólida de design system antes mesmo da implementação da lógica de negócio.

* **Link do Protótipo Interativo:** [Acessar v0.app](https://v0.app/chat/libri-share-platform-design-msPJcnG8O41?b=b_qAcFelQOQEo&f=1)
* **Referência Visual:** O design final segue as diretrizes estabelecidas no documento de especificação `LibriShare.pdf`.

### Telas Principais

O design foca em uma navegação lateral fixa e uso intensivo de modais para manter o contexto do usuário:

* **Navegação:** Menu lateral (Sidebar) persistente que fornece acesso rápido às seções principais: *Dashboard, Minha Biblioteca, Lendo Agora, Livros Lidos, Lista de Desejos e Empréstimos*.
* **Interatividade:** Ações críticas, como "Adicionar Livro" ou "Registrar Empréstimo", são realizadas através de **Dialogs (Modais)**, evitando recarregamentos de página desnecessários.
* **Tema:** Interface *Dark Mode* nativa para conforto visual durante leituras noturnas e uso prolongado.

---

## 🛠️ Tecnologias e Stack

A aplicação foi construída sobre o ecossistema React/Next.js:

| Tecnologia | Função |
| :--- | :--- |
| **Next.js 14** | Framework principal (App Router) para roteamento e renderização. |
| **TypeScript** | Garante a tipagem estática e segurança do código. |
| **Tailwind CSS** | Estilização utilitária para construção rápida de layouts. |
| **Shadcn/UI** | Biblioteca de componentes reutilizáveis (baseada em Radix UI). |
| **Lucide React** | Biblioteca de ícones leve e consistente. |
| **Zod** | Validação de esquemas e formulários (futuro). |

---

## 📂 Estrutura do Projeto

O código está organizado seguindo as melhores práticas do Next.js App Router:

```bash
librishare/
├── app/                    # Rotas da aplicação (File-system routing)
│   ├── layout.tsx          # Layout base (Sidebar, Toaster)
│   ├── page.tsx            # Landing Page / Login
│   ├── dashboard/          # Visão geral e estatísticas
│   ├── library/            # Grid de livros (Minha Biblioteca)
│   ├── reading/            # Controle de leitura em andamento
│   ├── loans/              # Gerenciamento de empréstimos
│   └── ...
├── components/             # Componentes React modularizados
│   ├── ui/                 # Componentes base do Shadcn (Button, Card, Input...)
│   ├── books/              # Componentes de negócio (AddBookDialog, BookDetail)
│   ├── dashboard/          # Widgets do dashboard (Sidebar, StatsCards)
│   └── loans/              # Lógica de empréstimos (LoanManagement)
├── hooks/                  # Custom Hooks
│   ├── use-user-id.ts      # Gerenciamento seguro do ID do usuário no cliente
│   ├── use-toast.ts        # Sistema de notificações
│   └── ...
└── lib/                    # Utilitários e configurações globais

```
-----

## 🔌 Integração com o Backend

A comunicação com a API Spring Boot é feita via `fetch` nativo do navegador, encapsulado em funções assíncronas dentro dos componentes ou hooks.

### Gestão de Estado e Sessão (MVP)

Para a versão 1.0, optou-se por uma autenticação simplificada baseada em identificador persistente:

1.  **Login:** O frontend valida o e-mail via API (`/users/search`).
2.  **Sessão:** O ID do usuário retornado é salvo no `localStorage` do navegador.
3.  **Hooks:** O hook customizado `useUserId` recupera esse ID para realizar todas as requisições autenticadas (ex: buscar biblioteca, criar empréstimo).
4.  **Feedback:** O sistema utiliza um componente `Toaster` global para fornecer feedback visual imediato (Sucesso/Erro) após cada interação com a API.

<!-- end list -->