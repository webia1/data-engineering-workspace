# Data Engineering Workspace

Detailed installation instructions (Docker Hadoop Cluster) can be found [here](https://dbis.pages.dbis-pro1.fernuni-hagen.de/docker-hadoop-cluster/).

## Quick Start

Starting the cluster (to run in background use: `docker-compose up -d`)

```bash
docker-compose up
```

> *NOTE:* Place your files (jupyter notebooks, etc.) under the `workspace/` folder

To start only the *client-node* (Jupyter-Notebook) if the Hadoop-Cluster is not needed:

```bash
docker-compose up client-node
```

To start the cluster with an alternative configuration for limited main memory:

```bash
docker-compose -f docker-compose.yml -f docker-compose-small.yml up
```

**WebUI-URL's:**

- Jupyter-Notebook: [**127.0.0.1:8888**](http://127.0.0.1:8888)
- Hadoop Resource-Manager: [**127.0.0.1:8088**](http://127.0.0.1:8088)

## Update to the Latest Release

First stop and delete the containers of the currently used version

```bash
docker-compose down
```

Then download the new tags from the remote server

```bash
git fetch --tags
```

Finally you can switch to the latest release (tag)

```bash
git checkout $(git tag | sort -V | tail -1)
```
