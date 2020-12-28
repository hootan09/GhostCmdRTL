### 1. Install yarn

```sh

curl -o- -L https://yarnpkg.com/install.sh | bash

```

### 2. Download the zip

```sh

curl -L https://ghost.org/zip/ghost-latest.zip -o ghost-latest.zip

unzip ghost-latest.zip -d ghost && cd ghost

```


### 3. Install dependencies

```sh

yarn install

```

### 4. Configuration

```sh

cp core/server/shared/config/env/config.production.json config.production.json

```

```sh
{
    "url": "<URL_OF_YOUR_BLOG>",
    "server": {
        "host": "127.0.0.1",
        "port": <DESIRED_PORT>
    },
    "database": {
        "client": "mysql",
        "connection": {
            "host"     : "127.0.0.1",
            "user"     : "<DB_USER>",
            "password" : "<DB_PASSWORD>",
            "database" : "<DB_NAME>"
        }
    },
    "auth": {
        "type": "password"
    },
    "paths": {
        "contentPath": "content/"
    },
    "logging": {
        "level": "info",
        "rotation": {
            "enabled": true
        },
        "transports": ["file", "stdout"]
    }
}

```

### 5. Knex migrator

```sh

sudo npm install -g knex-migrator --unsafe-perm

NODE_ENV=production knex-migrator init

```

### 6. Done

```sh

NODE_ENV=production node index.js

```



----------------------

## admin RTL

add style code in **adminRTL** file to ``C:\mywslLinux\Ghost-3.40.1\core\server\web\admin\views\default.html`` in head style

---------------------

## Support Persian lang

### ``Note the Default Theme not Suported Multi Language``

### 1. Create a locales folder and add language files

Create a folder called ``locales``. If using a theme that is already translatable, this may exist already.

Inside the locales folder, add target language files for each translatable language used on your site. For example ``locales/en.json`` for English and ``locales/es.json`` for Spanish. A valid language code must be used.

### 2. Translate included sentences

Translate the sentences used in your theme inside your new language files.

For example, in ``locales/en.json``:

```sh

{
    "Back": "Back",
    "Newer Posts": "Newer Posts",
    "Older Posts": "Older Posts",
    "Page {page} of {pages}": "Page {page} of {pages}",
    "Subscribe": "Subscribe",
    "Subscribe to {blogtitle}": "Subscribe to {blogtitle}",
    "Subscribed!": "Subscribed!",
    "with the email address": "with the email address",
    "Your email address": "Your email address",
    "You've successfully subscribed to": "You've successfully subscribed to",
    "A collection of posts": "A collection of posts",
    "A collection of 1 post": "A collection of 1 post",
    "A collection of % posts": "A collection of % posts",
    "Get the latest posts delivered right to your inbox": "Get the latest posts delivered right to your inbox",
    "Latest Posts": "Latest Posts",
    "<a href='{url}'>More posts</a> by {name}": "<a href='{url}'>More posts</a> by {name}",
    "No posts": "No posts",
    " (Page %)": " (Page %)",
    "Read More": "Read More",
    "Read <a href='{url}'>more posts</a> by this author": "Read <a href='{url}'>more posts</a> by this author",
    "See all % posts": "See all % posts",
    "Share this": "Share this",
    "Stay up to date! Get all the latest & greatest posts delivered straight to your inbox": "Stay up to date! Get all the latest & greatest posts delivered straight to your inbox",
    "This post was a collaboration between": "This post was a collaboration between",
    "youremail@example.com": "youremail@example.com",
    "1 post": "1 post",
    "% posts": "% posts",
    "1 min read": "1 min read",
    "% min read": "% min read"
}

```
