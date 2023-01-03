# FediSearch compose

This an example setup for Fediverse feed crawler and searcher.

Fedisearch consists of 4 app containers:
1. **Elasticsearch** - Key value storage database and fulltext search engine
2. **Fedistore** - Provides graphql api for searching and manimpulating with elastic storages
3. **Fedicrawl** - Crawls through the Fediverse network and stores all found nodes and also its feeds to database
4. **Fedisearch** - Web frontend for searching data in database

## Installation
App is designed primarily to be run in docker on linux. 
Thus `docker` and `docker-compose` are mandatory dependencies for this example setup.

I don't have prebuilt images in docker hub ready yet (but it's planned), so you have to build them locally. 
Docker compose should build images for you from sources...

1. Clone [fedisearch](https://github.com/Stopka/fedisearch), [fedicrawl](https://github.com/Stopka/fedicrawl) and [fedistore](https://github.com/Stopka/fedistore) apps to `./build` directory.
2. Copy `.env.dist` to `.env` and edit it as needed.
3. Create an `docker-compose.override.yml` file and override configuration by your liking.
You should at least add proxy (simple example is in `docker-compose.traefik.yml`) with tls termination.
4. Start the up by command
```docker compose up -d```

## Config
All configuration is done by env vars. 
Just edit `.env` file. 

Meaning of variables can be found in the readme files of
[fedisearch](https://github.com/Stopka/fedisearch), [fedicrawl](https://github.com/Stopka/fedicrawl)and [fedistore](https://github.com/Stopka/fedistore) apps.
