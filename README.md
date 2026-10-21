# .github

Repositorio de la organización Grupo-Tarahumara en GitHub.

## Contenido

| Ruta | Para qué sirve |
| ---- | -------------- |
| `profile/README.md` | Presentación que se muestra en la página pública de la organización. |
| `scripts/pr-check` | Comando para correr en local las validaciones de un PR y publicar el resultado en GitHub. |

> Este repositorio es público: no agregues información interna, credenciales ni datos de la empresa
> que no sean públicos.

## pr-check

Corre con [act](https://github.com/nektos/act) todos los workflows `pull_request` del repositorio
en el que estás y publica el resultado como el estado `pr-checks-local` en el último commit del PR,
que se pide para fusionar PRs hacia `develop`.

### Requisitos

- [GitHub CLI](https://cli.github.com/) (`gh`) con sesión iniciada
- [act](https://github.com/nektos/act)
- Docker en ejecución

### Instalación

```bash
git clone git@github.com:Grupo-Tarahumara/.github.git
cd .github
sudo install -m 755 scripts/pr-check /usr/local/bin/pr-check
```

Para actualizarlo, haz `git pull` y repite el `install`.

### Uso

Desde el repositorio del PR, con tu copia local en el último commit del PR y sin cambios pendientes:

```bash
pr-check        # usa el PR de la rama actual
pr-check 123    # o indica el número del PR
```

Cada commit nuevo reinicia el estado: vuelve a correr `pr-check` después de cada `push`.

## Contribuir

Trabaja en una rama `<tipo>/<CLAVE-JIRA>-<descripción>` (tipos: `feat`, `fix`, `chore`, `hotfix`,
`docs`, `release`) y abre un PR hacia `main`. Los commits siguen Conventional Commits con el emoji
después del tipo, por ejemplo `docs: 📝 actualiza el README`.
