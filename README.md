# 🛒 FSW Store - Full Stack E-commerce

![Next.js](https://img.shields.io/badge/Next.js-000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-3982CE?style=for-the-badge&logo=Prisma&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-626CD9?style=for-the-badge&logo=Stripe&logoColor=white)
![Auth](https://img.shields.io/badge/Next_Auth-000?style=for-the-badge&logo=nextdotjs&logoColor=white)

![App Screenshot](https://tone-monte-portfolio-v3.s3.us-east-1.amazonaws.com/projects/1758298651603-aed2sl-banner-fsw-store.png)

A **FSW Store** é uma plataforma de e-commerce de alto desempenho, desenvolvida com o objetivo de demonstrar padrões de arquitetura modernos no ecossistema **Full Stack Next.js**. O projeto foca em escalabilidade, responsividade impecável e uma experiência de usuário (UX) fluida, integrando pagamentos resilientes e autenticação segura.

---

## 🏗️ Arquitetura & Decisões Técnicas

Este projeto utiliza o que há de mais moderno no ecossistema React:

- **Next.js 15 (App Router)**: Aproveitamento total de _React Server Components (RSC)_ para performance superior e SEO otimizado, mantendo a interatividade apenas onde necessário.
- **Data Fetching Strategy**: Uso de _Server Effects_ e _Prisma ORM_ para comunicação direta com o banco de dados, reduzindo a latência de rede e simplificando a lógica de backend.
- **Design System com Shadcn/UI**: Componentes acessíveis (Radix UI) e estilização modular com Tailwind CSS, garantindo um código limpo e manutenível.
- **Padrão de Responsividade**: Layouts fluidos baseados no sistema de grades (CSS Grid) e flexbox, com estratégias específicas para Mobile, Tablet e Desktop de alta resolução.

---

## 🛠️ Funcionalidades Core

### 🛍️ Experiência de Compra

- **Catálogo Dinâmico**: Renderização híbrida para carregamento instantâneo.
- **Carrinho Inteligente**: Gerenciamento de estado global via Context API com persistência.
- **Checkout Resiliente**: Integração nativa com Stripe, tratando estados de sucesso e erro.

### 🔐 Segurança & Gestão

- **Autenticação SSO**: Login social via Google utilizando NextAuth.js.
- **Histórico de Pedidos**: Visualização detalhada de transações passadas.
- **Dashboards**: Interface administrativa para monitoramento de vendas e inventário.

---

## 📂 Estrutura de Pastas

A organização segue o padrão de **Clean Architecture** mínima para Next.js:

```bash
fsw-store/
├── prisma/               # Schema e Migrações (Single Source of Truth)
├── public/               # Ativos estáticos e Banners
├── src/
│   ├── app/              # Core da aplicação (Router, Layouts, Pages)
│   │   ├── (shop)/       # Grupo de rotas voltadas ao cliente final
│   │   ├── (admin)/      # Painel administrativo protegido
│   │   └── api/          # Endpoints de API (Webhooks, etc)
│   ├── actions/          # Server Actions para mutações de dados segura
│   ├── components/       # Componentes de UI (Atômicos e Moleculares)
│   │   └── ui/           # Componentes base do Shadcn/UI
│   ├── constants/        # Configurações globais e enums
│   ├── helpers/          # Funções utilitárias e cálculos puros
│   ├── lib/              # Instâncias de clientes e libs externas (Prisma, Stripe)
│   ├── providers/        # Contextos de estado global (Cart, Auth, Theme)
│   └── types/            # Definições de tipos TypeScript compartilhadas
```

---

## 💳 Dados para Teste (Stripe Sandbox)

Para simular transações no ambiente de desenvolvimento, utilize os seguintes dados:

| Campo          | Valor                              |
| :------------- | :--------------------------------- |
| **Cartão**     | `4242 4242 4242 4242`              |
| **Vencimento** | Qualquer data futura (ex: `12/30`) |
| **CVC**        | `123`                              |
| **CEP**        | `12345-678`                        |

---

## 🚀 Instalação e Configuração

### 1. Clonar e Instalar

```bash
git clone https://github.com/tonelopes/fsw-store.git
cd fsw-store
npm install
```

### 2. Variáveis de Ambiente (`.env`)

Configure o arquivo `.env` na raiz do projeto:

```env
# Database
DATABASE_URL="postgresql://user:password@localhost:5432/fsw_store"

# Stripe
NEXT_PUBLIC_STRIPE_PUBLIC_KEY="pk_test_..."
STRIPE_SECRET_KEY="sk_test_..."
STRIPE_WEBHOOK_SECRET_KEY="whsec_..."

# NextAuth
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="seu_secret_aqui"
GOOGLE_CLIENT_ID="..."
GOOGLE_CLIENT_SECRET="..."
```

### 3. Banco de Dados e Inicialização

```bash
# Sincronizar o schema com o banco de dados
npx prisma db push

# Popular o banco de dados (Seed) - OBRIGATÓRIO para ver os produtos e categorias
npm run db:seed

# Iniciar o servidor de desenvolvimento
npm run dev
```

---

## 📈 Próximos Milestones (Roadmap)

- [ ] Implementação de **Busca Full-Text** com filtros avançados.
- [ ] Sistema de **Avaliação de Produtos (Reviews)** com estrelas.
- [ ] **Modo Escuro (Dark Mode)** completo baseado em sistema/preferência do usuário.
- [ ] **Internacionalização (i18n)** para múltiplos idiomas e moedas.

---

## 🌐 Deploy

Confira a demonstração ao vivo: [FSW Store Production](https://fsw-store-xi-eight.vercel.app/)

---

