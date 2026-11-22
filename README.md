# Cadernos de Campo (site estático, sem build)

HTML, CSS e JavaScript puros. Sem Jekyll, sem instalar nada. Você controla cada pixel.

## Publicar no GitHub Pages
1. Crie um repositório e envie todos estes arquivos.
2. Settings > Pages > Deploy from a branch > `main` > `/ (root)`.
3. Os caminhos são relativos, então funciona em `usuario.github.io/repo` sem configurar nada.

Para testar no computador: `python3 -m http.server` e abra `http://localhost:8000`.

## Onde mexer
| Quero mudar...             | Arquivo                |
|----------------------------|------------------------|
| Cores, fontes, bordas      | `css/theme.css`        |
| Layout e componentes       | `css/style.css`        |
| Nome, menu, rodapé, sobre  | `js/config.js`         |
| Ilustrações em linhas      | `js/art.js`            |
| Estrutura de cada página   | `index.html`, `arquivo.html`, `post.html`, `sobre.html` |
| Novo texto                 | `posts/nome.md` + linha em `posts/posts.json` |

## Modelos de pastas
**A. Simples (este projeto):** `css/ js/ img/ posts/` na raiz.
**B. Por categoria:** `posts/pesquisa/`, `posts/processo/`; em `posts.json` use `"slug": "pesquisa/meu-texto"` (ajuste a regra de slug em `js/app.js`).
**C. Mídia organizada:** `img/capas/`, `img/posts/2026/`, `docs/`.
**D. Evoluir para framework:** se o blog crescer, mover para Astro ou Eleventy mantendo `css/` e `posts/`, com índice gerado automaticamente.
