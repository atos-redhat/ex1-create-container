# Ex. 1. Create Docker Container

## Steps to do

1. Use the `quay.io/redhattraining/httpd-parent` image with the `2.4` tag to start a new container named `httpd-basic` in the background. Forward port `8080` on the host to port `80` in the container.
    * Use the `podman run` command to start a container. Add the `-d` option to start it in the background and add the `-p` option to map port `8080` on the host to port `80` in the container.
    
2. Test that Apache HTTP server is running inside the `httpd-basic` container.
    * From your machine, attempt to access `http://localhost:8080` using any web browser.
    * A `Hello from the httpd-parent container!` message is displayed. This message is located on the `index.html` page from the Apache HTTP server container running on your machine.

3. Customize the `httpd-basic` container to display `Hello World` as the message. The container's message is stored in the file `/var/www/html/index.html`.
    * Start a `Bash` session inside the container.
    * From the `Bash` session, verify the `index.html` file under `/var/www/html` directory using the `ls -la` command.
    * Change the `index.html` file to contain the text `Hello World`, replacing all of the existing content.
    
4. Attempt to access `http://localhost:8080` again and verify that the web page has been updated.

## Useful commands

* `docker run -n <container_name> -p <host_port>:<container_port> <image>`
* `podman exec -it <container_name> /bin/bash` - start a `Bash` shell in the container, the `-it` flags specify start of the terminal session in the interative mode
* `vim <filename>` - to change a file in the container
