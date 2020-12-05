# git
basics

### Etapas
- Working dir
- Staging
- Repository

### Crear SSH Key y sincronizar con GitHub

https://help.github.com/es/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

https://help.github.com/es/articles/adding-a-new-ssh-key-to-your-github-account

### Comandos:

https://rogerdudler.github.io/git-guide/index.es.html

### Iniciar repositorio
```
git init
```

### Configurar usuario
```
git config --global user.name < name >
git config --global user.email < email >
```

### Ver configuración (user.name, user.email, etc)
```
git config --list
```

### Ver remote url
```
git config --get remote.origin.url
git remote show origin
```

### Cambiar remote url
```
git remote set-url origin < url >
```

### Listar stage
```
git diff --cached --name-only --diff-filter=[ACDMRTUXB*] 
```
https://stackoverflow.com/questions/2298047/git-ls-files-howto-identify-new-files-added-not-committed
https://stackoverflow.com/questions/6879501/filter-git-diff-by-type-of-change

### Limpiar stage
```
git rm --cached < file >
git reset HEAD -- < file >
git reset HEAD -- < directoryName >
```

### Listar commit local (?)
```
git ls-files
```

### Limpiar commit local
```
git reset --soft HEAD~1
git reset --hard origin/<branch>
```

### Cambiar branch
```
git checkout <branch>
git checkout -b <branch>
```

### Tag
```
git tag -a v1.0 -m ‘message’ 
```
