##Install docker 

```bash
sudo apt install docker.io docker-compose
```

## Manage Docker as a non-root user

To create the docker group and add your user:

    Create the docker group.
```bash
 sudo groupadd docker
```

Add your user to the docker group.
```bash 
 sudo usermod -aG docker $USER
```
Log out and log back in so that your group membership is re-evaluated.

    If you're running Linux in a virtual machine, it may be necessary to restart the virtual machine for changes to take effect.

You can also run the following command to activate the changes to groups:

```bash
 newgrp docker
```
Verify that you can run docker commands without sudo.

 docker run hello-world

This command downloads a test image and runs it in a container. When the container runs, it prints a message and exits.

If you initially ran Docker CLI commands using sudo before adding your user to the docker group, you may see the following error:

WARNING: Error loading config file: /home/user/.docker/config.json -
stat /home/user/.docker/config.json: permission denied

This error indicates that the permission settings for the ~/.docker/ directory are incorrect, due to having used the sudo command earlier.

To fix this problem, either remove the ~/.docker/ directory (it's recreated automatically, but any custom settings are lost), or change its ownership and permissions using the following commands:

 sudo chown "$USER":"$USER" /home/"$USER"/.docker -R

     sudo chmod g+rwx "$HOME/.docker" -R

Configure Docker to start on boot with systemd

Many modern Linux distributions use systemd

to manage which services start when the system boots. On Debian and Ubuntu, the Docker service starts on boot by default. To automatically start Docker and containerd on boot for other Linux distributions using systemd, run the following commands:

 sudo systemctl enable docker.service

 sudo systemctl enable containerd.service

To stop this behavior, use disable instead.

 sudo systemctl disable docker.service

 sudo systemctl disable containerd.service

You can use systemd unit files to configure the Docker service on startup, for example to add an HTTP proxy, set a different directory or partition for the Docker runtime files, or other customizations. For an example, see Configure the daemon to use a proxy.
Configure default logging driver

Docker provides logging drivers for collecting and viewing log data from all containers running on a host. The default logging driver, json-file, writes log data to JSON-formatted files on the host filesystem. Over time, these log files expand in size, leading to potential exhaustion of disk resources.

To avoid issues with overusing disk for log data, consider one of the following options:

    Configure the json-file logging driver to turn on log rotation.
    Use an alternative logging driver such as the "local" logging driver that performs log rotation by default.
    Use a logging driver that sends logs to a remote logging aggregator.
