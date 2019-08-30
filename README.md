# dockerXredis

# docker-compose purpose:

Split a project into several containers/instances (for example, multiple express instance with a single redis server)
Deal with multiple container networking better than docker-CLI

# How:

create a docker-compose.yml file:

version: '3'
services:
  redis-server:
    image: 'redis'
  node-app:
    restart: unless-stopped
    build: .
    ports:
      - "8081:8081"

# Optionnal:

define a restart policy:

"no"
always
on-failure
unless_stopped
