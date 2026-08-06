# BMW Leads — Setup GitHub Pages

## 1. Criar conta/repositório no GitHub

1. Vai a https://github.com e entra (ou cria conta)
2. Cria um novo repositório público chamado **`bmw-leads`**
3. Guarda o teu **username** do GitHub (ex: `ruimoutinho`)

---

## 2. Substituir d9vssghyk7-source nos ficheiros HTML

Em cada ficheiro `.html` (i3.html, etc.), substitui **`d9vssghyk7-source`** pelo teu username real:

```
https://d9vssghyk7-source.github.io/bmw-leads/images/i3.jpg
       ↓
https://ruimoutinho.github.io/bmw-leads/images/i3.jpg
```

Linhas a mudar (são 2 por ficheiro — og:image e og:url):
```html
<meta property="og:image" content="https://d9vssghyk7-source.github.io/bmw-leads/images/i3.jpg">
<meta property="og:url"   content="https://d9vssghyk7-source.github.io/bmw-leads/i3.html">
```

---

## 3. Obter a access key do Web3Forms

1. Vai a https://web3forms.com
2. Clica **Get your Access Key**
3. Introduz o email: **rui.moutinho@caetano.pt**
4. Vai ao email e copia a access key (formato: `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`)
5. Nos ficheiros HTML, substitui `YOUR_WEB3FORMS_ACCESS_KEY` pela tua chave:
   ```html
   <meta name="web3forms-key" content="TUA_CHAVE_AQUI">
   ```

---

## 4. Fazer push para o GitHub

```bash
cd /tmp/bmw-leads
git init
git add .
git commit -m "BMW leads landing pages"
git branch -M main
git remote add origin https://github.com/d9vssghyk7-source/bmw-leads.git
git push -u origin main
```

---

## 5. Ativar GitHub Pages

1. No repositório do GitHub, vai a **Settings → Pages**
2. Em "Branch", seleciona **main** e pasta **/ (root)**
3. Clica **Save**
4. Aguarda ~1 minuto e acede a: `https://d9vssghyk7-source.github.io/bmw-leads/i3.html`

---

## 6. Adicionar imagem do i3

Coloca uma foto do BMW i3 em:
```
/tmp/bmw-leads/images/i3.jpg
```
E volta a fazer push:
```bash
git add images/
git commit -m "Add i3 image"
git push
```

**Recomendações para a imagem:**
- Dimensão mínima: 1200×630 px (ratio 1.91:1 — ideal para OG preview)
- Fundo branco ou claro
- Formato JPG
- Tamanho máximo: 500 KB

---

## 7. Criar nova campanha

Duplica o ficheiro:
```bash
cp i3.html x1.html   # para um BMW X1, por exemplo
```

Edita apenas a secção no topo do ficheiro (os meta tags):
- `og:title`, `og:description`, `og:image`, `og:url`
- `modelo`, `tipo`, `badge`, `headline`, `subheadline`, `descricao`
- `imagem-caro` (aponta para o ficheiro em images/)

Adiciona a imagem correspondente em `images/` e faz push.

O link partilhável é:
```
https://d9vssghyk7-source.github.io/bmw-leads/x1.html
```

---

## Link partilhável (WhatsApp/SMS)

Ao partilhares o link no WhatsApp, ele faz o scrape automático das OG tags e gera um preview com:
- Imagem do carro
- Título (og:title)
- Descrição (og:description)

O cliente clica → abre a landing page → preenche o formulário → tu recebes email em rui.moutinho@caetano.pt
