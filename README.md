
- clone repo

- pull submodules

- build docker images
    docker compose build --no-cache


- update syxtrade config
    $cp src/syxtrade/config/config.sample.json src/syxtrade/config/config.json

- start docker containers
    docker compose up -d