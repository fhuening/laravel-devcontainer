# laravel-devcontainer
vscode php laravel devcontainer with apache, php8.2, mysql, redis and xcode debugger

First start:

- move .vscode from ./src to ./.devcontainer

- in vscode press F1 - Open Folder in Container

- build devcontainer

- after build, move .vscode folder from ./.devcontainer back to ./src

- open new terminal window in vscode in container

- change access:
```
chmod -R 755 /var/www/html
chown -R www-data:www-data /var/www/html
chmod -R 775 storage bootstrap/cache
```

Last step:
- edit your laravel .env file:

```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=root

REDIS_CLIENT=phpredis
REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379
```

Now in vscode press F1 and Rebuild Container

Go to ./src/routes/web.php and set breakpoint on line 6

After that, press ReOpen Container and then press F5 for debugging

Open browser with http://localhost and now the breakpoint should hit!


