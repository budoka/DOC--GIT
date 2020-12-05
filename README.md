# git
basics

#### Etapas
- Working dir
- Staging
- Repository

#### Crear SSH Key y sincronizar con GitHub

https://help.github.com/es/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
https://help.github.com/es/articles/adding-a-new-ssh-key-to-your-github-account

#### Comandos:

https://rogerdudler.github.io/git-guide/index.es.html

#### Iniciar repositorio
```
git init
```

#### Configurar usuario
```
git config --global user.name < name >
git config --global user.email < email >
```

#### Ver configuración (user.name, user.email, etc)
```
git config --list
```

## Remote

#### Agregar remote origin
```
git remote add origin < url >
```

#### Ver remote url
```
git config --get remote.origin.url
git remote show origin
```

#### Cambiar remote url
```
git remote set-url origin < url >
```

## Working Dir / Stage

#### Ver info
```
git show (información)
git status (estado actual)
```

#### Ver diferencia con `stage`
```
git diff
```

#### Listar `stage`
```
git diff --cached --name-only --diff-filter=[ACDMRTUXB*] 
```
https://stackoverflow.com/questions/2298047/git-ls-files-howto-identify-new-files-added-not-committed
https://stackoverflow.com/questions/6879501/filter-git-diff-by-type-of-change


#### Sacar archivo/s del `working dir` (los saca de git. No los elimina del directorio local)
```
git rm --cached < file/s >
```

#### Sacar archivo/s del `stage`
```
git restore --staged < file/s >
```

#### Resetear `working dir`
```
git restore < file/s >
```

#### Resetear `working dir` al último commit (borra todos los cambios hechos de git y `CÓDIGO`)
```
git reset --hard HEAD < file >
git reset --hard < commit hash >
```

#### Listar commit local (?)
```
git ls-files
```

#### Limpiar commit local
```
git reset --soft HEAD~1
git reset --hard origin/< branch >
```

#### Revertir commit (crea un nuevo commit revirtiendo/cancelando un commit - hacerlo con un commit viejo puede traer problemas-) 
```
git revert < commit hash >
```

## Rebase 

#### Rebase (interactivo)
```
git rebase -i
git rebase -i HEAD~N (pick ultimos N commits)  
```

## Branch

#### Crear branch
```
git branch < branch >
```

#### Borrar branch
```
git branch -d < branch >
```

#### Cambiar de branch
```
git checkout < branch >
```
#### Crear y cambiar a la branch
```
git checkout -b < branch >
```

#### Listar branchs
```
git branch
```

#### Mergear branch
```
git merge < branch >
```

#### Ver conflictos de branchs
```
git diff < source-branch > < target-branch >
```

## Tag

#### Tag
```
git tag -a v1.0 -m < message > 
```
