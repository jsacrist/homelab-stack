# Homelab stack

This repository contains a very simple `docker-compose.yml` file to quickly install a media server and companion applications.

## Basic usage

After cloning this repository to your server, create a file called `.env` inside of your repository directory, inside of this file define `MEDIA_DIR` like so:

```text
MEDIA_DIR=/path/to/your/stack/directory
```

NOTE: Replace `/path/to/your/stack/directory` with the actual path to your directory structure.

Your directory will end up looking something like this:

```text
.
├── appdata
│   ├── binhex-qbittorrentvpn
│   ├── seerr
│   ├── PlexMediaServer
│   ├── jellyfin
│   ├── portainer
│   ├── prowlarr
│   ├── radarr
│   └── sonarr
└── media
    ├── movies
    └── tv_shows
```

Subdirectories inside of `appdata` will be automatically created.

After that, simply run `docker compose up -d`, this will create the containers for each application, then and start configuring each application by going to the pointing your browser to the `address:port/` specified in each entry of `docker-compose.yaml`

## Common docker commands

NOTE: "Compose" commands (those starting with `docker compose`) need to be executed while in the directory of your compose yaml file.

| Command | Explanation |
| --- | --- |
| `docker compose start` | Starts existing containers for a service |
| `docker compose stop` | Stops running containers without removing them |
| `docker compose pause` | Pauses running containers of a service |
| `docker compose unpause` | Unpauses paused containers of a service |
| `docker compose up` | Builds, (re)creates, starts, and attaches to containers for a service |
| `docker compose up -d` | Builds, (re)creates, starts containers for a service (and detaches CLI)  Restarting on the latest version of images |
| `docker compose pull` | Pulls (downloads) images associated with a service defined in your compose yaml file |
| `docker compose down` | Stops containers, and removes containers, networks, volumes, and images created by `up` |
| - | - |
| `docker images` | Show a list of existing images |
| `docker rmi <IMAGE-ID>` | Remove the image given by `IMAGE-ID` from your system |
| `docker ps` | Show a list of containers currently running |
| `docker ps -a` | Show a list of all existing containers (even those not currently running) |
