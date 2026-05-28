# Otero — Web (Grúa, Mecánica e Chapa)

Sitio estático para **Otero** (Louredo, Maside): grúa, taller de mecánica e chapa. Publicado con [GitHub Pages](https://pages.github.com/).

Dominios previstos: **gruasotero.es** · **talleresotero.es**

## Ramas

| Rama      | Uso                                      |
|-----------|------------------------------------------|
| `develop` | Desenvolvemento e probas locais          |
| `main`    | Producción — é a que publica GitHub Pages |

Fluxo recomendado:

```bash
git checkout develop
# ... cambios ...
git add .
git commit -m "Describe o cambio"
git push origin develop

# Cando estea listo para publicar:
git checkout main
git merge develop
git push origin main
```

## Probar en local

Abre `index.html` no navegador ou usa un servidor simple:

```bash
cd /ruta/al/repo
python3 -m http.server 8080
# http://localhost:8080
```

## Publicar gratis en GitHub Pages

### 1. Activar GitHub Pages

1. Entra no repositorio en GitHub → **Settings** → **Pages**.
2. En **Build and deployment** → **Source**: elixe **Deploy from a branch**.
3. **Branch**: `main` · **Folder**: `/ (root)`.
4. Gardar. En 1–2 minutos a web estará en `https://<usuario>.github.io/otero/` (ou o nome do repo).

### 2. Dominio personalizado (gruasotero.es)

O ficheiro `CNAME` na raíz indica o dominio principal. En **Settings → Pages → Custom domain** escribe `gruasotero.es` e activa **Enforce HTTPS** cando estea dispoñible.

**DNS no teu rexistrador** (exemplo para dominio raíz):

| Tipo  | Nome | Valor              |
|-------|------|--------------------|
| `A`   | `@`  | `185.199.108.153`  |
| `A`   | `@`  | `185.199.109.153`  |
| `A`   | `@`  | `185.199.110.153`  |
| `A`   | `@`  | `185.199.111.153`  |

Ou con **CNAME** (subdominio `www`):

| Tipo   | Nome | Valor                    |
|--------|------|--------------------------|
| `CNAME`| `www`| `<usuario>.github.io`    |

IPs oficiais: [documentación GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).

### 3. Segundo dominio (talleresotero.es)

GitHub Pages só permite **un** dominio no ficheiro `CNAME`, pero podes apuntar **os dous** dominios ao mesmo sitio:

1. No rexistrador de **talleresotero.es**, usa as **mesmas** entradas `A` (ou `CNAME` a `<usuario>.github.io`).
2. En GitHub → **Settings → Pages → Custom domain**, engade tamén `talleresotero.es` se a interface o permite, ou deixa só `gruasotero.es` no CNAME — ambos DNS ao mesmo repo funcionan igual.

Comproba con `dig gruasotero.es` e `dig talleresotero.es` que resolven ás IPs de GitHub.

### 4. HTTPS

Tras configurar DNS, espera a validación (ata 24 h). Activa **Enforce HTTPS** en Pages.

## Estrutura

```
├── index.html
├── css/styles.css
├── js/main.js
├── assets/          # logos, favicon, cartel
├── CNAME            # dominio principal Pages
└── README.md
```

## Licenza

Uso privado do negocio Otero.
