# Site do Prof. Rodrigo Nogueira Cardoso

Site de materiais didáticos e pesquisa, construído com
[MkDocs Material](https://squidfunk.github.io/mkdocs-material/) e hospedado
gratuitamente no GitHub Pages.

---

## 🚀 Como publicar (passo a passo)

### Pré-requisitos

- Uma conta no [GitHub](https://github.com) (gratuita)
- Nada mais. Você não precisa instalar nada no seu computador.

### Passo 1 — Criar o repositório no GitHub

1. Acesse [github.com/new](https://github.com/new)
2. Em **Repository name**, escolha um nome (sugestão: `materiais` ou `site-rodrigo`)
3. Marque **Public** (precisa ser público para usar o GitHub Pages gratuito)
4. **NÃO** marque "Add a README file"
5. Clique em **Create repository**

Depois de criar, anote dois valores que vão aparecer na URL:

- **Seu usuário do GitHub** (ex.: `rodrigo-nc`)
- **Nome do repositório** (ex.: `materiais`)

### Passo 2 — Subir os arquivos

Há duas formas. Escolha a mais confortável:

#### Forma A — Pela interface do GitHub (mais fácil, sem instalar nada)

1. Na página do repositório recém-criado, clique em **uploading an existing file**
2. Arraste **TODOS os arquivos e pastas** desta pasta para o navegador
   (incluindo os ocultos `.github/` e `.gitignore`)
3. Em "Commit changes", escreva: `Versão inicial do site`
4. Clique em **Commit changes**

> ⚠️ **Importante**: a interface web do GitHub às vezes ignora pastas ocultas
> (como `.github/`). Se notar que o deploy automático não está funcionando,
> use a Forma B abaixo ou crie a pasta `.github/workflows/` manualmente
> pelo botão "Add file > Create new file" no GitHub.

#### Forma B — Pelo Git (recomendado se você já usa)

```bash
cd /caminho/para/esta/pasta
git init
git add .
git commit -m "Versão inicial do site"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git
git push -u origin main
```

### Passo 3 — Ativar o GitHub Pages

1. No repositório, vá em **Settings** (Configurações)
2. No menu lateral, clique em **Pages**
3. Em **Source**, selecione **GitHub Actions**
4. Pronto. Não precisa configurar mais nada aqui.

### Passo 4 — Personalizar (importante!)

Antes do primeiro deploy, edite o arquivo `mkdocs.yml` e substitua os
campos abaixo pelo seu usuário e nome de repositório:

```yaml
site_url: https://SEU-USUARIO.github.io/SEU-REPOSITORIO/
repo_name: SEU-USUARIO/SEU-REPOSITORIO
repo_url: https://github.com/SEU-USUARIO/SEU-REPOSITORIO
```

E nas redes sociais (também em `mkdocs.yml`):

```yaml
extra:
  social:
    - icon: fontawesome/brands/github
      link: https://github.com/SEU-USUARIO
    # ... etc
```

### Passo 5 — Acompanhar o deploy

1. Vá na aba **Actions** do repositório
2. Você verá um workflow chamado "Deploy MkDocs site to Pages" rodando
3. Quando terminar (✅ verde), seu site estará no ar em:

   ```
   https://SEU-USUARIO.github.io/SEU-REPOSITORIO/
   ```

4. Pronto! Tempo total de deploy: cerca de 1-2 minutos.

---

## ✏️ Como editar o conteúdo

Cada página é um arquivo `.md` (Markdown — texto simples) dentro da pasta `docs/`.

### Editando direto no GitHub (mais fácil)

1. Navegue até o arquivo no GitHub
2. Clique no ícone do lápis (✏️) no canto superior direito
3. Edite o conteúdo
4. Em "Commit changes", escreva uma descrição da alteração
5. Clique em **Commit changes**
6. Em ~1 minuto o site estará atualizado

### Editando localmente

Se preferir editar no computador:

```bash
# Instalar dependências (uma vez só)
pip install -r requirements.txt

# Rodar servidor local com preview ao vivo
mkdocs serve
```

Acesse `http://127.0.0.1:8000` no navegador. As alterações aparecem
automaticamente.

Quando terminar, faça commit e push:

```bash
git add .
git commit -m "Atualização de conteúdo"
git push
```

---

## 📁 Estrutura do projeto

```
.
├── mkdocs.yml                    # Configuração principal (cores, menu, etc)
├── requirements.txt              # Dependências Python
├── .github/workflows/deploy.yml  # Deploy automático
├── docs/
│   ├── index.md                  # Página inicial
│   ├── sobre.md                  # Página "Sobre"
│   ├── disciplinas/              # Materiais das disciplinas
│   │   ├── automacao-industrial/
│   │   └── outras/
│   ├── pesquisa/                 # Linha de pesquisa, publicações
│   ├── extras/                   # Recomendações e ferramentas
│   ├── assets/                   # PDFs, imagens, downloads
│   ├── stylesheets/extra.css     # Customização visual
│   └── javascripts/mathjax.js    # Configuração de LaTeX
```

---

## 💡 Dicas úteis

### Adicionando um PDF para download

1. Coloque o arquivo em `docs/assets/` (ex.: `docs/assets/apostila.pdf`)
2. Em qualquer página, escreva:
   ```markdown
   [Baixar apostila (PDF)](../../assets/apostila.pdf)
   ```

### Adicionando uma imagem

1. Coloque a imagem em `docs/assets/`
2. Escreva: `![Descrição](../../assets/imagem.png)`

### Escrevendo equações (LaTeX)

```markdown
Inline: \( F = m \cdot a \)

Bloco:

\[
\sum_{i=1}^{n} x_i = x_1 + x_2 + \cdots + x_n
\]
```

### Criando blocos destacados

```markdown
!!! note "Observação"
    Conteúdo da nota.

!!! warning "Atenção"
    Aviso importante.

!!! tip "Dica"
    Sugestão útil.
```

### Diagramas (Mermaid)

````markdown
```mermaid
graph LR
    A[Sensor] --> B[CLP]
    B --> C[Atuador]
```
````

---

## 🆘 Problemas comuns

**O site não atualiza após o commit**

Vá na aba **Actions** e veja se o workflow falhou. Clique no workflow
vermelho para ver o erro.

**Erro de build "strict mode"**

Algum link está quebrado. O log do Actions mostra qual arquivo. Corrija
e faça novo commit.

**404 ao acessar o site**

Confirme que em **Settings > Pages** a fonte está definida como
**GitHub Actions** (não "Deploy from a branch").

---

## 📚 Documentação completa

- [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) — tema usado
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/) — sintaxe Markdown
- [GitHub Pages](https://docs.github.com/pt/pages) — hospedagem

---

*Construído com ❤️ por Rodrigo Nogueira Cardoso — IFTM Campus Ituiutaba.*
