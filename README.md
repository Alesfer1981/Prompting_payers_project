# Prompting_payers_project

Este repositorio contiene la documentación de IA y *prompting* exportada desde Notion y preparada para publicarse con **GitHub Pages**.

## Estructura

- `docs/`: Contenido principal en Markdown.
  - `index.md`: Página de inicio con un índice agrupado por temas (LLM, RAG, Prompting, etc.).
  - Otros `.md`: Páginas individuales de tu investigación.
  - `assets/icons/`: Carpeta lista para que agregues íconos personalizados.
- `_config.yml`: Configuración mínima para GitHub Pages usando el tema `jekyll-theme-cayman`.

## Cómo publicarlo en GitHub Pages

1. Crea un repositorio en GitHub llamado `Prompting_payers_project`.
2. Sube todo el contenido de esta carpeta al repositorio.
3. En GitHub, ve a **Settings → Pages**.
4. En **Build and deployment**, selecciona:
   - Source: `Deploy from branch`
   - Branch: `main`
   - Folder: `/docs`
5. Guarda los cambios.

Tras unos minutos, tu sitio estará disponible en una URL similar a:

`https://<tu-usuario>.github.io/Prompting_payers_project/`

La página de inicio será `docs/index.md`, que contiene el índice con enlaces al resto del contenido.
