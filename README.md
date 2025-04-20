# laravel-devcontainer
vscode php laravel devcontainer with apache, php8.2, mysql, redis and xcode debugger

First start:

- move .vscode from ./src to ./.devcontainer

- in vscode press F1 - Open Folder in Container

- build devcontainer

- after build, move .vscode folder from ./.devcontainer back to ./src

- open new terminal window in vscode in container

- change access to:

- chmod -R 755 /var/www/html
  
- chown -R www-data:www-data /var/www/html
  
- chmod -R 775 storage bootstrap/cache
  
- in vscode press F1 and Rebuild Container


