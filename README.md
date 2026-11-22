# Cadernos de Campo (site estático, sem build)

HTML, CSS e JavaScript puros. Sem Jekyll, sem instalar nada. Você controla cada pixel.

## Publicar (uma vez só)
1. Crie um repositório e envie todos estes arquivos (inclusive a pasta oculta `.github`).
2. Settings > Pages > **Source: GitHub Actions**.
3. Pronto. A cada commit na `main`, a Action em `.github/workflows/publicar.yml` gera o índice dos textos e publica o site. O andamento aparece na aba Actions.

## Publicar um texto novo (no dia a dia)
1. No GitHub, abra a pasta `posts` > Add file > Create new file.
2. Nome do arquivo: letras sem acento, números e hífen, terminando em `.md` (ex.: `meu-texto.md`).
3. Cole o conteúdo (cabeçalho + texto) e faça o commit. Em cerca de 1 minuto o texto está no ar.
Arquivos que começam com `_` (como `_modelo.md`) são ignorados.

Para testar no computador: `node scripts/build-index.mjs` e depois `python3 -m http.server`.

## Onde mexer
| Quero mudar...             | Arquivo                |
|----------------------------|------------------------|
| Cores, fontes, bordas      | `css/theme.css`        |
| Layout e componentes       | `css/style.css`        |
| Nome, menu, rodapé, sobre  | `js/config.js`         |
| Ilustrações em linhas      | `js/art.js`            |
| Estrutura de cada página   | `index.html`, `arquivo.html`, `post.html`, `sobre.html` |
| Novo texto                 | `posts/nome.md` (cabeçalho com título, subtítulo, categoria, data) |
| Como o índice é montado    | `scripts/build-index.mjs` |

## Modelos de pastas
**A. Simples (este projeto):** `css/ js/ img/ posts/` na raiz.
**B. Por categoria:** `posts/pesquisa/`, `posts/processo/`; ajuste o script de índice e a regra de slug em `js/app.js`.
**C. Mídia organizada:** `img/capas/`, `img/posts/2026/`, `docs/`.
**D. Evoluir para framework:** se o blog crescer, mover para Astro ou Eleventy mantendo `css/` e `posts/`, com índice gerado automaticamente.
