
# 🎯 Desafio Técnico (fullstack) – Frontend do Sistema de Gerenciamento de Voluntários

## 📋 Sobre o Desafio

Você deverá desenvolver o **frontend** de um Sistema de Gerenciamento de Voluntários que consumirá uma API REST já existente.
Este desafio avaliará seus conhecimentos em **React, Vite, TypeScript, gerenciamento de estado, UI, organização do código e boas práticas**.

### 🎨 Referência de Design

O layout da aplicação deve seguir como referência o modelo disponível no Figma:
**[https://www.figma.com/design/JO0vsAS75zlc0Vrx0tA5WZ/Desafio-Desenvolvedor-junior?node-id=0-1&t=OiZVkJwKOB4I7uSH-1](https://www.figma.com/design/JO0vsAS75zlc0Vrx0tA5WZ/Desafio-Desenvolvedor-junior?node-id=0-1&t=OiZVkJwKOB4I7uSH-1)**

⏱️ **Prazo de Entrega:**
12 dias a partir do recebimento deste desafio.
---

### 🚨 REQUISITO OBRIGATÓRIO: VITE **OU** NEXT.JS

O projeto **deve obrigatoriamente** ser desenvolvido usando **React com TypeScript**, podendo ser criado de duas formas:

### ✔ **Opção A — Vite + React + TypeScript**

*(configuração mais simples e rápida — recomendada)*

### ✔ **Opção B — Next.js + TypeScript**

*(permitido para quem preferir estrutura com rotas nativas e SSR/ISR)*

Em ambas as opções, o uso de **TypeScript é obrigatório**.
---

# 🎯 Objetivo

Criar um painel administrativo simples para:

* Cadastrar voluntários
* Listar voluntários
* Filtrar voluntários
* Atualizar dados
* Inativar voluntários (soft delete)

## 📌 Campos do voluntário:

* nome (obrigatório)
* email (obrigatório)
* telefone (obrigatório)
* cargo_pretendido (obrigatório)
* disponibilidade (opções fixas)
* status (ativo/inativo)
* data de inscrição (somente leitura)

---

# 🚀 Requisitos Técnicos do Frontend

## 1. Stack Obrigatória

* **React**
* **Vite**
* **TypeScript**
* **TanStack Query** (para consumo da API)
* **Axios** (ou Fetch)
* **TailwindCSS** 
* **Componente UI**

---

## 2. Funcionalidades Obrigatórias

### ✔ CRUD Completo

* Criar voluntário
* Listar voluntários
* Editar voluntário
* Inativar voluntário (soft delete)

### ✔ Filtros na listagem

* status
* cargo
* disponibilidade
* busca por nome ou email

### ✔ Formulário com validação

* Validação no frontend
* Exibir erro de email duplicado (409) vindo da API

### ✔ Estados visuais

* Loading
* Empty state
* Error state
* Feedbacks (toast)

### ✔ Organização do código

Estrutura clara e componentizada.

---

# 🔧 REQUISITOS DE IMPLEMENTAÇÃO

## 1. Telas Obrigatórias

### 📝 **1. Listagem de Voluntários**

* Tabela com nome, email, telefone, cargo, disponibilidade, status e data
* Botão para **criar voluntário**
* Botão para **editar**
* Botão para **inativar**
* Filtros avançados (status, cargo, disponibilidade)

---

### ➕ **2. Cadastro de Voluntário**

* Formulário completo
* Validação de campos obrigatórios
* Envio POST para a API

---

### ✏️ **3. Edição de Voluntário**

* Formulário populado
* PUT para atualizar
* Permitir alterar status

---

### 👁️ **4. Visualização Detalhada** *(opcional, mas diferencial)*

---

Aqui está a seção revisada **exatamente como pediu**, deixando claro que **o candidato deve consumir a própria API que ele mesmo desenvolveu no desafio backend**, eliminando a opção de mock e reforçando que **o frontend depende diretamente da API criada por ele**.

---

## 2. Integração com a API

O frontend **deve obrigatoriamente consumir a API FastAPI criada pelo próprio candidato** no desafio backend.
Não será permitido uso de mocks, JSON Server ou qualquer API externa.

### ✔ Requisitos de Integração

* A API deve estar rodando localmente (ex: `http://localhost:8000`)
* O frontend deve consumir *exatamente* os endpoints definidos no desafio backend
* Configurar um arquivo `.env` contendo a URL base da API:

```
VITE_API_URL=http://localhost:8000
```

* Recomenda-se o uso de React Query (TanStack Query) para:

  * requisições
  * cache
  * estados de loading / error
  * invalidação após mutações

## 3. Estrutura mínima do Projeto

A seguinte estrutura é sugerida:

```
src/
├── api/
│   ├── volunteers.ts
│   └── apiClient.ts
├── components/
├── hooks/
│   └── useVolunteers.ts
├── pages/
│   ├── VolunteersList/
│   ├── VolunteerCreate/
│   ├── VolunteerEdit/
├── App.tsx
└── main.tsx
```

---

# 📁 Exemplos de Endpoints

Utilize a seguinte estrutura como referência:

```
GET    /voluntarios
GET    /voluntarios/{id}
POST   /voluntarios
PUT    /voluntarios/{id}
DELETE /voluntarios/{id}
```

---

# ✅ Critérios de Avaliação

## Avaliação Técnica (80% da nota)

### 🎯 **Obrigatórios (50% da nota)**

* Uso correto do Vite
* Tela de listagem
* Criar voluntário
* Editar voluntário
* Soft delete funcionando
* Filtros funcionando
* React Query implementado corretamente
* Validação de formulários

---

### ⭐ **Diferenciais (30% da nota)**

* Tratamento elegante de erros da API
* UI consistente (shadcn/ui, Chakra, Radix, etc)
* Loading skeleton
* Paginação
* Deploy (Vercel/Netlify)
* Testes (Vitest + Testing Library)

---

## Avaliação de Boas Práticas (20% da nota)

* Código limpo, organizado e legível
* Componentização correta
* Pastas e arquivos bem estruturados
* Commits descritivos
* README claro

---

# 🧪 Testes (Opcional, mas somam pontos)

Sugestão de testes:

```ts
test("deve criar voluntário com dados válidos", () => {});
test("não deve permitir email duplicado", () => {});
```

---

# 📤 Como Entregar

## 1. Repositório Git (OBRIGATÓRIO)

* Publique no GitHub/GitLab
* Commits frequentes
* Branch main limpa

---

## 2. README Obrigatório

Inclua no README:

* Como rodar o projeto:

  ```
  pnpm install
  pnpm dev
  ```
* Como configurar `.env`
* Lista de páginas
* Estrutura de pastas
* Decisões técnicas
* Se usou mock, como rodar

---

## 3. Entrega Final

Envie para: **[claudiosilva.one@gmail.com](mailto:claudiosilva.one@gmail.com)**

Inclua:

* Link do repositório
* Observações importantes
* Se usou mock ou integrou com a API real

Preencha também o Forms de Entrega:
🔗 [https://forms.gle/Rpj82v33CoB8tRea8](https://forms.gle/Rpj82v33CoB8tRea8)

---

# 🆘 Dicas Importantes

### Foque no básico:

* CRUD funcionando
* Filtros
* UX limpa
* React Query bem implementado

### O que avaliamos:

* Domínio de React
* Organização
* Capacidade de seguir especificações
* Boas práticas de código
* Uso correto da stack proposta

### Não precisa:

* Autenticação
* Context API se React Query já resolver
* Design complexo
