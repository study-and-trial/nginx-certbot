# Boilerplate for nginx with Let’s Encrypt on docker-compose

> This repository is accompanied by a [step-by-step guide on how to
> set up nginx and Let’s Encrypt with Docker](https://medium.com/@pentacent/nginx-and-lets-encrypt-with-docker-in-less-than-5-minutes-b4b8a60d3a71).

`init-letsencrypt.sh` fetches and ensures the renewal of a Let’s
Encrypt certificate for one or multiple domains in a docker-compose
setup with nginx.
This is useful when you need to set up nginx as a reverse proxy for an
application.

## Installation

1.  Install docker to use **docker compose**

2.  Clone this repository at the server

    - which is forked from [wmnnd/nginx-certbot](https://github.com/wmnnd/nginx-certbot.git)

3.  Be sure that apps are running on the server

4.  Modify configuration:

    - Add domains and email addresses to init-letsencrypt.sh
    - Replace all occurrences of example.org with primary domain (the first one you added to init-letsencrypt.sh) in data/nginx/app.conf
    - Set upstreams' name and port in data/nginx/app.conf for running apps

5.  Set ports open to public, usually 80 and 443

6.  Run the init script:

        ./init-letsencrypt.sh

7.  Run the server:

        docker-compose up -d

## Got questions?

Feel free to post questions in the comment section of the [accompanying guide](https://medium.com/@pentacent/nginx-and-lets-encrypt-with-docker-in-less-than-5-minutes-b4b8a60d3a71)

## License

All code in this repository is licensed under the terms of the `MIT License`. For further information please refer to the `LICENSE` file.
