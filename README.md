# symfony5
Docker for symfony 5/php 7.4 with:
- composer
- yarn
- nodejs
- npm
- pandoc
- ghostscript
- memcache
- opcache
- mbstring
- wget
- curl
- imagemagick
- git
- tree
- nano
- environnement PANTHER
- php.iuni
- apache.conf

## execution in your symfony directory
`
docker run -d -p 80:80  --name symfony5 -v .:/app cadoteu/symfony5
`
## or by docker-compose with traefik
```bash
...
image: cadoteu/symfony5 
    container_name: symfony5-php7
    volumes:
      - /home/ubuntu/my_symfony:/app
    networks:
      - web
    restart: always
    labels:
        - "traefik.enable=true"
        - "traefik.http.routers.symfony5.rule=Host(`symfony5.website.com`)"
...
```
