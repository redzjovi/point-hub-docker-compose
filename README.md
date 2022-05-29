# misteraladin-magiclamp

## How to use

Build

```bash
docker-compose build
```

Do not use cache when building the image.

```bash
docker-compose build --no-cache
```

Stops containers and removes containers, networks, volumes, and images created by up

```bash
docker-compose down
```

Builds, (re)creates, starts, and attaches to containers for a service.

```bash
docker-compose up
```

Detached mode: Run containers in the background, print new container names.

```bash
docker-compose up -d
```

My custom and favorite

```bash
docker-compose down && docker-compose up -d
docker-compose down && docker-compose up -d mysql nginx
```
