# Canvas scraper

## Please double-check the data

Two reasons:

1. This script does not save resources to which you do not have access.
Pending further updates to the code, you need to manually ensure the script
has downloaded all the resources from Canvas!

2. Often professors will embed videos that require authentication to view, etc.
At time of writing, this script does not handle such embeds.
Please make sure you can view all resources without authentication before
considering the export done
.

## Docker
A Docker image is provided for convenience. You can configure it to write to a
data directory of your choice. To make a data directory named `data` and bind
mount it to the Docker container, perform the following commands:

`mkdir ./data`

```
docker run \
  -u "$(id -u)" \
  -v "$(pwd)"/data:/usr/src/app/data \
  johnhix/scrape-canvas:0.0.3 \
  https://institution.canvas-address.edu \
  canvas-api-key \
  ./data \
  all

```
The last option, `all`, can be replaced with a comma-separated list
of course ids.
