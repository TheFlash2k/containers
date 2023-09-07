# CTFd Docker Containers Plugin

This CTFd plugin allows you to run ephemeral Docker containers for specific challenges. Teams can request a container to use as needed, and its lifecycle will be managed by the plugin.

## Installation

Configure CTFd:
- Map docker socket into CTFd container by modifying the `docker-compose.yml` file:
```docker
services:
  ctfd:
    ...
    volumes:
    ...
      - /var/run/docker.sock:/var/run/docker.sock
    ...
```

Add plugin to CTFd:
- Clone this repository
- Rename "CTFd-Docker-Plugin" to "containers"
- Place `containers` folder inside `CTFd/plugins` directory

## Usage

*Note: Currently the plugin only works with team mode*

Connect to Docker daemon:
- If the CTFd and the challenges host in the same machine, you just need to go to the plugin page in admin page, click on `Settings`, on this page just fill in other fields except the `Base URL` field.
![](https://cdn.discordapp.com/attachments/1120761462600777869/1149367147231985714/image.png)

- If you host the CTFd and the challenges in different machines, you need to follow the instructions one that page

Create the challenge:

- Select container type and fill all the required fields
![](https://cdn.discordapp.com/attachments/1120761462600777869/1149367426241273876/image.png)

![](https://cdn.discordapp.com/attachments/1120761462600777869/1149367639345463316/image.png)

- If you want regular scoring for the challenge, set the maximum and minimum values to the same amount and the decay to zero.

- In the image field, it allows you to select the docker image already on the machine


## Some demo

![](./demo.gif)
