# 🤖 LeadFlow — Site Estático para GitHub Pages

Landing page premium da LeadFlow, pronta para publicação **gratuita** no GitHub Pages.  
Nenhum servidor, nenhuma hospedagem paga, nenhum banco de dados.

---

## 📁 Estrutura de Arquivos

```
leadflow-site/
├── index.html        ← Página principal (landing page completa)
├── obrigado.html     ← Página de confirmação após envio do formulário
└── README.md         ← Este guia
```

---

## 🚀 PASSO A PASSO — Publicar no GitHub Pages

### PASSO 1 — Criar conta no GitHub

1. Acesse **https://github.com**
2. Clique em **"Sign up"** (canto superior direito)
3. Preencha: e-mail, senha, nome de usuário
4. Confirme seu e-mail (chegará uma mensagem na caixa de entrada)
5. Sua conta está criada ✅

---

### PASSO 2 — Criar o repositório

1. Faça login em **https://github.com**
2. Clique no botão verde **"New"** (ou no **"+"** no canto superior direito → "New repository")
3. Preencha:
   - **Repository name:** `leadflow-site`
   - **Description:** Site LeadFlow — Automação de Atendimento com IA
   - Marque **"Public"** (obrigatório para GitHub Pages gratuito)
   - **NÃO** marque "Add a README file"
4. Clique em **"Create repository"** ✅

---

### PASSO 3 — Enviar os arquivos

Você tem duas opções:

#### ▶ Opção A — Pelo site (mais simples, sem programar nada)

1. Na página do repositório recém-criado, clique em **"uploading an existing file"**
2. Arraste ou selecione os arquivos:
   - `index.html`
   - `obrigado.html`
3. Na caixa **"Commit changes"**, deixe a mensagem padrão ou escreva "Primeiro upload"
4. Clique em **"Commit changes"** ✅

#### ▶ Opção B — Pelo terminal (Git)

```bash
git clone https://github.com/SEU_USUARIO/leadflow-site.git
cd leadflow-site
# Cole os arquivos index.html e obrigado.html nesta pasta
git add .
git commit -m "Deploy inicial LeadFlow"
git push origin main
```

---

### PASSO 4 — Acessar Settings → Pages

1. No repositório `leadflow-site`, clique na aba **"Settings"** (ícone de engrenagem)
2. No menu lateral esquerdo, clique em **"Pages"**

---

### PASSO 5 — Configurar a publicação

Em **"Build and deployment"**:

| Campo | Valor |
|-------|-------|
| **Source** | Deploy from a branch |
| **Branch** | main |
| **Folder** | / (root) |

Clique em **"Save"** ✅

---

### PASSO 6 — Aguardar publicação

- O GitHub levará **1 a 3 minutos** para publicar o site
- Você verá uma mensagem azul: *"Your site is being built"*
- Quando estiver pronto, aparecerá em verde: *"Your site is live at..."*

---

### PASSO 7 — URL pública do seu site

Após a publicação, seu site estará disponível em:

```
https://SEU_USUARIO.github.io/leadflow-site/
```

**Exemplo:** se seu usuário GitHub for `weslley`, a URL será:
```
https://weslley.github.io/leadflow-site/
```

> 💡 **Dica:** Atualize os links no código substituindo `seuusuario` pelo seu nome de usuário real do GitHub.

---

## ✉️ CONFIGURAR O FORMULÁRIO (Formspree)

O formulário de contato usa o **Formspree** — serviço gratuito que recebe envios de formulários sem precisar de backend.

### Como configurar (5 minutos):

1. Acesse **https://formspree.io** e crie uma conta gratuita (usa seu e-mail)
2. Clique em **"New Form"**
3. Dê um nome ao formulário (ex: "LeadFlow Demo")
4. O Formspree gerará um ID parecido com: `xrgwkpqz`
5. Abra o arquivo `index.html` e localize as linhas:

```html
action="https://formspree.io/f/YOUR_FORM_ID"
```

6. Substitua `YOUR_FORM_ID` pelo seu ID real. Exemplo:

```html
action="https://formspree.io/f/xrgwkpqz"
```

> Faça isso em **dois lugares** no arquivo: no formulário da seção CTA e no formulário do modal.

7. Também substitua nos campos `_next`:

```html
value="https://seuusuario.github.io/leadflow-site/obrigado.html"
```

Pelo seu usuário real do GitHub.

8. Salve e faça o upload novamente para o GitHub ✅

> **Plano gratuito do Formspree:** 50 envios/mês. Para mais envios, use o plano pago ou configure outra solução.

---

## 🔧 PERSONALIZAÇÕES RÁPIDAS

### Trocar número do WhatsApp
Busque no `index.html` por `5548988088068` e substitua pelo seu número (com DDI e DDD, sem espaços ou traços).

### Trocar texto da mensagem do WhatsApp
Busque por `Ol%C3%A1%21%20Tenho%20interesse` — esse texto está codificado (URL encode).  
Para gerar seu próprio link com mensagem personalizada, acesse:  
**https://wa.me/** e use ferramentas como https://urlencode.io

### Trocar URL do site (SEO)
Busque por `seuusuario.github.io` e substitua pelo seu usuário real do GitHub.

### Adicionar vídeo de demonstração
Na seção `#demo` do `index.html`, substitua o bloco `.demo-area` por:

```html
<div class="demo-area" style="padding:0">
  <iframe
    width="100%" height="420"
    src="https://www.youtube.com/embed/SEU_VIDEO_ID"
    frameborder="0"
    allowfullscreen
    style="border-radius:0 0 20px 20px">
  </iframe>
</div>
```

---

## 🌐 USANDO DOMÍNIO PRÓPRIO (opcional)

Se você tiver um domínio como `leadflow.com.br`:

1. No seu provedor de domínio (Registro.br, GoDaddy, etc.), configure um registro DNS:
   - Tipo: `CNAME`
   - Nome: `www`
   - Valor: `SEU_USUARIO.github.io`

2. No GitHub Pages → **Settings → Pages → Custom domain**, insira seu domínio.

3. Marque **"Enforce HTTPS"** para certificado SSL gratuito ✅

---

## 📊 ANALYTICS GRATUITO (opcional)

Para saber quantas pessoas visitam seu site, adicione antes do `</head>` no `index.html`:

```html
<!-- Google Analytics (substitua G-XXXXXXXXXX pelo seu ID) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

Crie sua conta gratuita em: **https://analytics.google.com**

---

## ✅ CHECKLIST FINAL

Antes de divulgar o site, confirme:

- [ ] `YOUR_FORM_ID` substituído pelo ID real do Formspree
- [ ] `seuusuario` substituído pelo seu usuário GitHub em todos os links
- [ ] Número do WhatsApp correto (`5548988088068`)
- [ ] Site abre corretamente em `https://seuusuario.github.io/leadflow-site/`
- [ ] Formulário de contato chega no e-mail do Formspree
- [ ] Botão "Falar no WhatsApp" abre conversa corretamente
- [ ] Página `obrigado.html` carrega após envio do formulário
- [ ] Site abre bem no celular

---

## 📞 Suporte

WhatsApp: [+55 48 98808-8068](https://wa.me/5548988088068)

---

*LeadFlow — Automação Inteligente para Empresas © 2025*
