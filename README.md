# Portal Copa 2026 — Deploy no Vercel

## Estrutura da pasta

```
portal-copa-2026-deploy/
├── index.html        ← o portal completo
├── vercel.json       ← configuração de rotas
├── api/
│   └── scan.js       ← proxy seguro para a API da Anthropic
└── README.md
```

---

## Passo a passo completo

### 1. GitHub — criar repositório

1. Acesse **github.com** e faça login (ou crie uma conta)
2. Clique em **"New"** (botão verde)
3. Nome: `portal-copa-2026`
4. Deixe **Public** (necessário para o plano gratuito do Vercel)
5. Clique **"Create repository"**
6. Na tela seguinte, clique em **"uploading an existing file"**
7. **Arraste todos os arquivos desta pasta** (index.html, vercel.json, e a pasta api/)
8. Clique **"Commit changes"**

### 2. Vercel — conectar e fazer deploy

1. Acesse **vercel.com** → **"Add New Project"**
2. Clique **"Continue with GitHub"** e autorize
3. Selecione o repositório `portal-copa-2026`
4. Clique **"Deploy"** — aguarde ~30 segundos

### 3. Vercel — configurar a API Key (IMPORTANTE)

1. No painel do projeto no Vercel, clique em **"Settings"**
2. Clique em **"Environment Variables"**
3. Adicione:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** sua chave `sk-ant-...`
   - Marque os ambientes: Production, Preview, Development
4. Clique **"Save"**
5. Volte em **"Deployments"** → clique nos 3 pontos do último deploy → **"Redeploy"**

### 4. Pronto!

Você terá uma URL pública tipo `portal-copa-2026.vercel.app` que:
- Funciona em qualquer dispositivo / navegador
- O scanner de imagem funciona para todos os usuários
- Sua API Key está segura no servidor — ninguém consegue ver

---

## Como atualizar o portal

Sempre que o Claude gerar um novo `index.html`:
1. Vá no repositório GitHub
2. Clique no arquivo `index.html`
3. Clique no ícone de lápis (editar)
4. Cole o novo conteúdo → **"Commit changes"**
5. O Vercel faz o redeploy automaticamente em ~30 segundos

---

## Onde pegar a API Key

https://console.anthropic.com/settings/keys
