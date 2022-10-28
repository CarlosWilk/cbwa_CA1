# docker-static-website

A very small Docker image (~154KB) to run any static website, based on the [BusyBox httpd](https://www.busybox.net/) static file server.

Download the folder html

Build the image:

```sh
docker build -t my-static-website .
```

Run the image:

```sh
docker run -it --rm --init -p 8080:8080 my-static-website
```

Browse to `http://localhost:8080`.


# Docker security measures
To protect the container I changed the root user to static

# References list
Bmwitcher (2020). Deploying a Static Website In a Docker Container: [online] Warp 9. Available at: https://medium.com/warp9/deploying-a-static-website-in-a-docker-container-f6b7d8eed15f [Accessed 26 Oct. 2022].

G, D. (2018). What Is the Wget Command and How to Use It (12 Examples Included). [online] Hostinger Tutorials. Available at: https://www.hostinger.com/tutorials/wget-command-examples/ [Accessed 26 Oct. 2022].

Lipan, F. (2021). The smallest Docker image to serve static websites. [online] Florin Lipan. Available at: https://lipanski.com/posts/smallest-docker-image-static-website [Accessed 25 Oct. 2022].

Seven Bridges (2022). Create and upload a Docker image with a Dockerfile. [online] Seven Bridges. Available at: https://docs.sevenbridges.com/docs/upload-your-docker-image-with-a-dockerfile [Accessed 26 Oct. 2022].

Srivastav, P. (2018). A Docker Tutorial for Beginners. [online] A Docker Tutorial for Beginners. Available at: https://docker-curriculum.com/#webapps-with-docker [Accessed 26 Oct. 2022].

TecAdmin.net (2020). Deploy A Static Website with Docker. [online] TecAdmin. Available at: https://tecadmin.net/tutorial/docker-run-static-website [Accessed 25 Oct. 2022].
