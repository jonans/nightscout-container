# Nightscout for Containers

Run [Nightscout](http://www.nightscout.info/) in containers using Docker Swarm or Compose

Makes use of Caddy webserver for automatic registration of TLS certificates with Lets Encrypt.

The following images are used:

 - https://hub.docker.com/r/nightscout/cgm-remote-monitor
 - https://hub.docker.com/r/bitnami/mongodb
 - https://hub.docker.com/_/caddy

## Setup

   1. Copy vars.sample to vars and set the required variables.

   1. Add any other nightscout variables as needed. https://github.com/nightscout/cgm-remote-monitor#environment

   1. Start nightscout with docker swarm or compose:

      - Compose:

        `docker-compose up`

      - Swarm:

        `docker stack deploy -c docker-compose.yml nightscout`

   1. When ready for production use make sure to:
       - Set the DOMAIN variable in vars
       - Comment out the acme_ca line in Caddyfile


