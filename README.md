# Prompting Payers Project (Just the Docs)

Este repositorio está preparado para usarse con el tema **Just the Docs** en GitHub Pages.

## Estructura

- `_config.yml`: Configuración del sitio (título, descripción, tema, URL/baseurl).
- `docs/`:
  - `index.md`: Página de inicio.
  - Páginas seccionales con `has_children: true` (IA, LLM, RAG, Prompting, Frameworks, Federated).
  - Páginas hijas con `parent:` apuntando a cada sección.
  - Imágenes exportadas desde Notion en la raíz de `docs/`.

## Publicación en GitHub Pages

1. Crea un repositorio en GitHub llamado `Prompting_payers_project`.
2. Sube todo el contenido de esta carpeta.
3. En GitHub, ve a **Settings → Pages**.
4. En **Build and deployment**, selecciona:
   - Source: `Deploy from branch`
   - Branch: `main`
   - Folder: `/docs`
5. Guarda los cambios.

El sitio quedará disponible en:

`https://<tu-usuario>.github.io/Prompting_payers_project/`

con un sidebar jerárquico y búsqueda habilitada gracias a **Just the Docs**.
