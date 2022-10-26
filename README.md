# docker-static-website

A very small Docker image (~154KB) to run any static website, based on the [BusyBox httpd](https://www.busybox.net/) static file server.


For more details, check out the article(https://lipanski.com/posts/smallest-docker-image-static-website).

## Usage

The image is hosted on [Docker Hub](https://hub.docker.com/r/lipanski/docker-static-website):

```dockerfile
FROM lipanski/docker-static-website:latest

# Copy your static files
COPY . .
```

Build the image:

```sh
docker build -t my-static-website .
```

Run the image:

```sh
docker run -it --rm -p 8080:80 my-static-website
```

Browse to `http://localhost:8080`.

If you need to configure the server in a different way, you can override the `CMD` line:

```dockerfile
FROM lipanski/docker-static-website:latest

# Copy your static files
COPY . .

CMD ["/busybox", "httpd", "-f", "-v", "-p", "3000", "-c", "httpd.conf"]
```

**NOTE:** Sending a `TERM` signal to your TTY running the container won't get propagated due to how busybox is built. Instead you can call `docker stop` (or `docker kill` if can't wait 15 seconds). Alternatively you can run the container with `docker run -it --rm --init` which will propagate signals to the process correctly.

# Docker security measures

to protect the container I changed the root user to static