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

#### Permite agregar nuevos archivos al commit y modificar el mensaje
```
git commit --amend
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

#### Revertir commit (vuelve a un commit anterior y luego borra los archivos creados posteriormente al commit) 
```
git reset --hard < commit hash >
git clean -f
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
git branch -D < branch >
```

#### Borrar branch remoto
```
git push origin --delete < branch > 
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

#### Listar todos los branchs (local y remoto)
```
git branch -a
```

#### Renombrar branch
```
git branch -m < old-name > < new-name >
```

#### Mergear branch
```
git merge < branch >
```

#### Ver conflictos de branchs
```
git diff < source-branch > < target-branch >
```

#### Copiar archivos de otro branch 
```
git checkout < branch > < files >
```

## Tag

#### Tag
```
git tag -a v1.0 -m < message > 
```

#### Push tag to remote
```
git push origin < tag > 
```

#### Delete Tag
```
git tag -d < tag > 
```


#### Delete Tag
```
git push --delete origin < tag >
```


#### Limpiar historial de commits:
1) `git checkout -b < temp-branch >`
2) `git rebase -i HEAD~N` (pick ultimos N commits)
3) *Cuando se abra la interfaz, el primer commit en pick y los demás en splash/fixup. Cerrar archivo. Si no se resuelve automáticamente corregir con `git rebase --edit-todo`, corregir y luego `git rebase --continue`*
4) Cambiar el branch default remoto en GitHub por otro que no sea master
5) `git push origin --delete master`
6) `git branch -m < old-name > < new-name >` (debería ser `git branch -m < temp-branch > master`)
7) `git push origin master`
