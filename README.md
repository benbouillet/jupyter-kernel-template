# jupyter-kernel-template
---

_This repository acts as scaffold to implement a Python project with an emphasis on separating the development environment (with JupyterLab) and the production environment. Both of them are containerized._

## Architecture

The `kernel` folder acts as the entrypoint for the production dependencies defined in the Dockerfile.

The `jupyterlab` folder acts as the entrypoint for the development environment.

`jupyterlab` is built **on top of `kernel`** to:
* avoid injecting development dependencies into the target production deployment
* have a reproducible environment between development & production

## Usage

### Building both images

```bash
docker compose build
```

### Running JupyterLab

```bash
docker compose up
```

JupyterLab is then accessible at [http://localhost:8888](http://localhost:8888).


## Caveats

The JupyterLab workflow is **not** expected to be deployed anywhere but on a local machine. It does not provide any authentication mechanism or HTTPS/TLS encryption.
