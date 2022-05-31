# Chrome Web Store Stats


## Run locally
    
    # setup environment
    mkdir -p src/data/{config,metadata}

    # you can use an example config
    # you'll need to set the SMTP/StatsD credentials though
    cp example/config.js src/data/config/example.js

    # move to src dir
    cd src

    # install deps
    npm install

    # run one of the following commands, e.g. from cmd or by cron
    node index.js -c example.js --email
    node index.js -c example.js --statsd
    node index.js -c example.js --email --statsd
    

## Run via Docker Compose

    # setup environment
    mkdir -p data/{config,metadata}

    # you can use an example config
    # you'll need to set the SMTP/StatsD credentials though
    cp examples/config.js data/config/example.js

    # create crontab file
    cp examples/crontab data/crontab


### Run via crontab

    # start container
    docker-compose [-p chrome-web-store-stats] up [--build] [--detach]


### Run specific command

    # run command
    docker-compose run --entrypoint="node /app/index.js -c example.js --email" app
