# TiddliWiki 5 Docker image

Run TiddlyWiki 5 via Docker.

'Borrowed' from 
The Docker image is available at [m0wer/tiddlywiki - Docker
Hub](https://hub.docker.com/r/m0wer/tiddlywiki).

Only changed the port to 8090.

## Prerequisites

* Docker.

## Quickstart

```bash
docker run -d -p 8090:8090 m0wer/tiddlywiki
```

Now TiddlyWiki should be running on
[http://localhost:8090](http://localhost:8090).

## Keeping the data

The container uses a Docker volume to save the wiki data. In order not
to lose sight of that, I recommend using a local directory for the volume.

```bash
docker run -d -p 8090:8090 -v $(pwd)/.tiddlywiki:/var/lib/tiddlywiki m0wer/tiddlywiki
```

In this example, the folder `$(pwd)/.tiddlywiki` is used for the data.

## Authentication

Default credentials are `user`:`wiki`.

Simply provide the `USERNAME` and `PASSWORD` environment variables to
customize.

## Other settings

### Limit Node.js memory

If you are in a memory-constrained environment, you can provide the
`NODE_MEM` environment variable to specify the memory ceiling (in MB)

### Debug

Set the `DEBUG_LEVEL` environment variable to `debug`. For example by passing
`-e DEBUG_LEVEL=debug` option in `docker run`.
