# git
basics

# Crear SSH Key y sincronizar con GitHub

https://help.github.com/es/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

https://help.github.com/es/articles/adding-a-new-ssh-key-to-your-github-account

# Comandos:

https://rogerdudler.github.io/git-guide/index.es.html

# Ver remote url

git config --get remote.origin.url
git remote show origin

# Cambiar remote url

git remote set-url origin <url>

# Limpiar commit local

git reset --hard origin/<branch>
