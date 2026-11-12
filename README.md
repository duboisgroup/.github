# .github

Ficheros por defecto de la organización `duboisgroup`.

GitHub usa estos ficheros en cualquier repositorio de la organización que no tenga los suyos propios:

- `pull_request_template.md`: plantilla de los pull requests. Las tareas se enlazan con su id de ClickUp (`DEV-###`).

Para cambiar la plantilla de todos los repos, se cambia aquí. Un repo que necesite una distinta puede tener su propio `.github/pull_request_template.md`, y entonces GitHub usa la del repo.

La plantilla solo se rellena sola al abrir el PR desde la web o con `gh pr create` interactivo. Con `gh pr create --body`/`--body-file` o con la API hay que escribir el cuerpo con este mismo formato.
