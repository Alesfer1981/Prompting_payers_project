# Prompting Payers Project (Just the Docs + imágenes organizadas)

Este repositorio está preparado para usarse con el tema **Just the Docs** en GitHub Pages,
con las imágenes organizadas por tema en `docs/assets/images/<tema>/`.

## Estructura

- `_config.yml`: Configuración del sitio (título, descripción, tema, URL/baseurl).
- `docs/`:
  - `index.md`: Página de inicio.
  - Páginas seccionales con `has_children: true` (IA, LLM, RAG, Prompting, Frameworks, Federated).
  - Páginas hijas con `parent:` apuntando a cada sección.
  - Imágenes en:
    - `assets/images/ia/`
    - `assets/images/llm/`
    - `assets/images/rag/`
    - `assets/images/prompting/`
    - `assets/images/frameworks/`
    - `assets/images/federated/`
    - `assets/images/shared/` (si alguna imagen se usa en más de un tema)

## Publicación en GitHub Pages

1. Crea un repositorio en GitHub llamado `Prompting_payers_project` (o usa el existente).
2. Sube todo el contenido de esta carpeta.
3. En GitHub, ve a **Settings → Pages**.
4. En **Build and deployment**, selecciona:
   - Source: `Deploy from branch`
   - Branch: `main`
   - Folder: `/docs`
5. Guarda los cambios.

El sitio quedará disponible en:

`https://<tu-usuario>.github.io/Prompting_payers_project/`

con un sidebar jerárquico y todas las imágenes funcionando desde carpetas organizadas.
