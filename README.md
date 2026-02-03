# 🤖 Gmail AI Auto-Reply Bot (n8n + Google Gemini)

Automação criada no **n8n** que monitora novos e-mails no Gmail e responde automaticamente usando um **agente de IA (Google Gemini)**, com memória de conversa por thread.  
Ideal para atendimento inicial, respostas a dúvidas frequentes e automação de pré-vendas.

---

## ✨ Funcionalidades

- 📥 Escuta novos e-mails via **Gmail Trigger**
- 🧠 Geração de respostas automáticas com **IA (Google Gemini)**
- 💬 Memória de contexto por thread (conversas contínuas)
- 📤 Resposta automática ao remetente
- 🧹 Filtro para ignorar domínios específicos (ex: e-mails internos)
- 🧩 Workflow modular e fácil de adaptar

---

## 🧱 Arquitetura do Workflow

Fluxo principal:

Gmail Trigger → IF (filtro de remetente) → AI Agent (Gemini + Memory) → Reply to Message (Gmail)

Componentes:
- **Gmail Trigger**: detecta novos e-mails
- **IF**: filtra remetentes (ex: ignora domínio específico)
- **AI Agent (LangChain)**: gera a resposta
- **Google Gemini Chat Model**: modelo de IA
- **Simple Memory**: memória por threadId
- **Gmail (Reply)**: envia a resposta

---

## 🚀 Como rodar o projeto localmente

### 1️⃣ Pré-requisitos

- Conta no **n8n** (cloud ou self-hosted)
- Conta Google com acesso ao **Gmail API**
- Chave de API do **Google Gemini**

---

### 2️⃣ Importar o Workflow no n8n

1. Abra o n8n
2. Clique em **Import workflow**
3. Selecione o arquivo `gmail-ai-auto-reply.json.json`

---

### 3️⃣ Configurar Credenciais

Após importar, o n8n vai pedir:

- 🔐 **Gmail OAuth2**
- 🔐 **Google Gemini API Key**

> ⚠️ As credenciais não estão no repositório por segurança.

---

### 4️⃣ Ajustar Regras de Filtro (Opcional)

No nó **IF**, você pode configurar:
- Domínios a ignorar (ex: `@suaempresa.com`)
- Regras para responder apenas a certos remetentes

---

### 5️⃣ Ativar o Workflow

Depois de configurar tudo:
- Clique em **Activate**
- O bot passa a responder automaticamente os novos e-mails 🎉

---

## 📝 Observações

- O workflow pode ser expandido para outros modelos de IA ou integrações.
- Recomenda-se revisar as respostas automáticas antes de uso em produção.

---

## 📄 Licença

MIT

---

## 🛡️ Segurança

- Nenhuma credencial é versionada no repositório
- O workflow foi sanitizado para uso público
- Recomenda-se usar variáveis de ambiente para produção

---

## 📁 Estrutura do Repositório

```
gmail-ai-auto-reply.json.json   # Workflow n8n
README.md                      # Documentação
```

---

## 🧪 Casos de uso

- Atendimento inicial automático
- Pré-vendas de cursos/produtos
- Respostas a dúvidas frequentes
- Suporte básico via e-mail
- Prototipagem de agentes de IA

---

## 🧠 Melhorias Futuras (ideias)

- Classificação de e-mails por intenção
- Integração com CRM
- Base de conhecimento com RAG
- Logs de conversas em banco de dados
- Modo humano para handoff

---

## 👨‍💻 Paula Sabino

Projeto desenvolvido como demonstração de automação com IA e n8n para portfólio.

Se quiser trocar uma ideia ou evoluir o projeto, bora! 🚀
