# imóvelAI — Cadastro automático de imóveis

App que usa IA para extrair dados de mensagens do WhatsApp e preencher cadastros no CRM imobiliário.

---

## Como colocar no ar (Vercel) — passo a passo

### 1. Criar conta no GitHub
Acesse https://github.com e crie uma conta gratuita se ainda não tiver.

### 2. Criar repositório no GitHub
1. Clique em **New repository**
2. Nome: `imovelai`
3. Deixe como **Public** ou **Private** (tanto faz)
4. Clique em **Create repository**

### 3. Fazer upload dos arquivos
Na página do repositório criado, clique em **uploading an existing file** e suba os arquivos:
```
imovelai/
├── vercel.json
├── api/
│   └── analyze.js
└── public/
    └── index.html
```
Clique em **Commit changes**.

### 4. Criar conta no Vercel
Acesse https://vercel.com e crie conta gratuita (pode entrar com o GitHub).

### 5. Importar projeto
1. No Vercel, clique em **Add New Project**
2. Selecione o repositório `imovelai` do GitHub
3. Clique em **Deploy** (sem mudar nada)

### 6. Configurar a API Key da Anthropic
1. No Vercel, vá em **Settings → Environment Variables**
2. Adicione:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** sua chave (começa com `sk-ant-...`)
3. Clique em **Save**
4. Vá em **Deployments** e clique em **Redeploy** para aplicar

### 7. Acessar o app
O Vercel vai te dar uma URL tipo:
```
https://imovelai.vercel.app
```
Pronto! Compartilhe essa URL com os corretores.

---

## Como pegar a API Key da Anthropic
1. Acesse https://console.anthropic.com/settings/keys
2. Crie uma conta se necessário
3. Clique em **Create Key**
4. Copie a chave e cole no Vercel (passo 6 acima)

---

## Estrutura do projeto
```
api/analyze.js     → Função serverless que chama a API da Anthropic com segurança
public/index.html  → O app completo (frontend)
vercel.json        → Configuração de rotas do Vercel
```

---

## Custo estimado
- Vercel: **gratuito** para esse volume de uso
- API Anthropic: ~R$ 0,05 por cadastro processado (muito barato)
