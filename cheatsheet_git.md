## Usando Git Bash

### Traer ramas de repositorio github a local 
- git fetch

### Una vez traidas las ramas de github, usar en repositorio local
- git checkout -t origin/{nombre_rama_de_github}

### Consultar ramas actuales repositorio local
- git branch

### Saltar a rama local
- git checkout {nombre_rama_local}

### Actualizar ramas de local a github
- git push origin {nombre_rama_github}

### Treaer datos de github a local
- git pull origin {nombre_rama_github}


### Hacer mersh dos ramas en local (desde rama destino)

- git merge --no-commit {nombre_de_la_otra_rama}


### Crear tag (se debe estar en rama pertinente)

- git tag -a {nombre_tag} -m "{comentario_tag}"

### Subir todos los tags locales

- git push origin --tags
