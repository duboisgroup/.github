# .github

Ficheros por defecto de la organización `duboisgroup`.

GitHub usa estos ficheros en cualquier repositorio de la organización que no tenga los suyos propios:

- `pull_request_template.md`: plantilla de los pull requests. Las tareas se enlazan con su id de ClickUp (`DEV-###`).

Para cambiar la plantilla de todos los repos, se cambia aquí. Un repo que necesite una distinta puede tener su propio `.github/pull_request_template.md`, y entonces GitHub usa la del repo.

La plantilla solo se rellena sola al abrir el PR desde la web o con `gh pr create` interactivo. Con `gh pr create --body`/`--body-file` o con la API hay que escribir el cuerpo con este mismo formato.

## Convenciones de nombres

Valen para todos los repos de la organización.

### Commits

[Conventional commits](https://www.conventionalcommits.org/es/): `tipo(ámbito): descripción`. Los tipos son `feat`, `fix`, `perf`, `refactor`, `chore`, `docs`, `style`, `test` y `ci`, y el ámbito es opcional. Al CHANGELOG solo van `feat`, `fix` y `perf`. git-cliff descarta los commits que no siguen este formato, así que no salen en el CHANGELOG. También descarta formatos parecidos, como `feat - lidia: …`.

### Título del PR

El mismo formato que un commit, con la tarea al final entre paréntesis:

```
tipo(ámbito): descripción (DEV-###)
```

Por ejemplo, `fix(claims): archivado de documentos sin intercambiar name y code (DEV-281)`. Si no hay tarea, se omite el paréntesis.

El título tiene que ser un commit convencional válido porque, si el PR se mergea con squash, GitHub lo usa como asunto del commit, y git-cliff lo descartaría si no lo es. No vale poner la tarea en otro sitio: ni `DEV-### · descripción`, ni `tipo(DEV-###): …`, ni `tipo(ámbito): DEV-### descripción`.

### Rama

```
tipo/DEV-###-slug
```

`tipo` es el mismo que en el título y `slug` es una descripción corta en minúsculas con guiones, por ejemplo `fix/DEV-281-archivado-documentos`. Si no hay tarea: `tipo/slug`.

### Tarea de ClickUp

- El nombre es una frase descriptiva sin el `DEV-###`: ClickUp ya muestra el id.
- En las listas que mezclan productos o clientes, el nombre lleva delante el producto, como en `Toro: …` o `Myrtea: …`.
- Las subtareas numeradas de un proyecto se llaman `N · título`, como las de LidIA.
- La descripción enlaza los PR.
