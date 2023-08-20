# moebius-dev
Dev setup for moebius and moebius-api

# How to setup
- git submodule update --init --recursive
- cp ./env_files/moebius-db/.env.dist ./env_files/moebius-db/.env
- cp ./env_files/moebius-api/.env.dist ./env_files/moebius-api/.env
- cp ./env_files/moebius/.env.dist ./env_files/moebius/.env
- docker-compose up -d

# How to start development
## For moebius
- docker exec -it moebius bash
- cd moebius 
- check moebius README.md on how to run it

## For moebius-api
- docker exec -it moebius-api bash
- cd moebius-api
- // TODO