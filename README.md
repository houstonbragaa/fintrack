# Fintrack

Fintrack é uma aplicação web para controle e visualização das suas finanças pessoais, com foco em simplicidade e experiência de uso. Permite o cadastro de ganhos, gastos e investimentos, exibe dashboard intuitivo, gráficos e uma tabela detalhada de transações.

## 🚀 Visão Geral

- Cadastro e autenticação de usuários com tokens JWT
- Dashboard interativo: saldo, ganhos, gastos, investimentos e gráficos
- Adição, edição e visualização de transações financeiras
- Filtros por período para balanços e histórico

---

## 😎 Demonstração Visual

<img src="/src/assets/Logo.svg" height="48" />

- **Dashboard:** Resumo do saldo, gráfico de pizza (ganhos, gastos, investimentos), cards e tabela de transações
- **Autenticação:** Telas de login e cadastro
- **Fluxo protegido:** Usuário não autenticado é redirecionado para o login
- **Página 404:** Exibe aviso de rota inexistente

---

## 🧭 Estrutura de Telas e Navegação

- `/login`: Tela de autenticação de usuário
- `/signup`: Cadastro de novo usuário
- `/`: Dashboard financeiro (após login)
- `*`: Página de rota não encontrada

### Dashboard Principal

- Header fixo com avatar e acesso ao logout
- Cards-resumo: saldo, ganhos, gastos, investimentos
- Gráfico de pizza para visualização rápida
- Filtros de data para histórico
- Botão para adicionar nova transação
- Tabela listando todas as transações do período

---

## 🔐 Autenticação e Segurança

- Utiliza JWT (access/refresh token) no localStorage
- Middleware integra tokens a cada request protegido
- Refresh automático ao expirar o access token
- Rotas protegidas via contexto de autenticação (`AuthContextProvider`)
- Logout limpa tokens e dados locais

---

## 🌐 API Utilizada

- Base: [`https://fullstackclub-finance-dashboard-api.onrender.com/api`](https://fullstackclub-finance-dashboard-api.onrender.com/api)

Exemplos de endpoints:

- `POST /users` – Criação de usuário
- `POST /users/login` – Login JWT
- `GET /users/me` – Dados do usuário autenticado
- `GET /transactions/me` – Lista de transações do usuário
- `POST /transactions/me` – Adiciona transação
- `PATCH /transactions/me/:id` – Edita transação

Tokens são enviados automaticamente pelo frontend.

---

## 📁 Estrutura de Pastas (resumida)

```
src/
  api/            # hooks e serviços para requisições
  assets/         # imagens e fontes
  components/     # sistemas de UI e funcionalidades
  constants/      # constantes globais (ex: tokens)
  contexts/       # Providers (ex: Auth)
  forms/          # hooks e schemas de formulários
  helpers/        # utilitários (datas, moedas)
  pages/          # páginas/router
  lib/            # configurações globais (ex: axios)
```

---

## 🛠️ Tecnologias

- **React 18** + Vite
- **TailwindCSS** (UI moderna)
- **React Query** (requisições e cache de dados)
- **Axios** (HTTP requests)
- **Shadcn / Lucide** (componentes e ícones)
- **Zod** (validação)
- **date-fns** (datas e internacionalização)
- **ESLint/Prettier** (qualidade/código limpo)

---

## ⚙️ Como rodar o projeto

1. Clone o repositório e instale as dependências:
   ```bash
   npm install
   ```
2. Inicie o modo desenvolvimento:
   ```bash
   npm run dev
   ```
3. Acesse [http://localhost:5173](http://localhost:5173)

> Você pode criar conta à vontade: todos os dados ficam na API pública.
> Não precisa rodar backend localmente.

---

## ✍️ Como contribuir

- Fork ou clone
- Crie novos componentes em `src/components` quando possível
- Mantenha uma branch por funcionalidade
- Use Commits descritivos

---

## 📌 Observações Técnicas

- Tokens seguros no localStorage (access/refresh)
- Atualização automática de tokens expirados
- Responsividade por padrão
- Código comentado nas principais funções

---

## 📚 Referências, dicas e links

> A aplicação consome a API já hospedada remotamente. Não é necessário rodar o backend localmente.

---

Projeto criado para estudos e portfólio. Dúvidas ou sugestões? Fique à vontade para abrir issues!
