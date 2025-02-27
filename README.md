# Dynalite Docker Image

TL;DR:

```
docker pull ghcr.io/hennge/dynalite
```

## Notice 

We're taking over the maintenance of this repo from [dimaqq](https://github.com/dimaqq/dynalite-docker).
Thank you for maintaining this repo this whole time 🙏.

## Details

https://github.com/HENNGE/dynalite-docker/pkgs/container/dynalite

Docker container for latest `dynalite` (https://github.com/mhart/dynalite).

With sane default settings: port 8000 and no artificial delay.

Example use:

```
docker pull ghcr.io/hennge/dynalite
```

Persistent data mode:

```
docker run --init -p 8000:8000 -v /tmp/somewhere:/data ghcr.io/hennge/dynalite --path /data
```

Integration into docker-compose, for automated tests:

```yaml
  dynalite:
    image: ghcr.io/hennge/dynalite
    init: true
    ports:
      - "8000:8000"
```

Testing or building locally:

```yaml
  dynalite:
    build: dynalite-docker
    init: true
    ports:
      - "8000:8000"
```

## Changes

* `3.2.2`: Node 18, `dynalite=3.2.2`
* `3.2.1`: Node 17, `dynalite=3.2.1`
* `3.2.1`: Node 14, `dynalite=3.2.1`
* `3.0.0`: Node 12, `dynalite=3.0.0`
* `2.3.0`: Node 11, `dynalite=2.3.0`

## Arch

* `amd64`
* `arm64`

### 2.x Notes:

> Please ignore the deprecation warnings during build\
> leveldown@5.0.0 should address those\
> dynalite@next will eventually pull in new leveldown
