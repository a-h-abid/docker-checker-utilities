# Checker Utilities

A simple containerization script with useful tools like ncat, telnet, ping etc. Useful during checking connectivity from container / pod to destination.

**Base:** `debian`

**Tools installed:**
- vim
- nano
- curl
- ncat
- telnet
- ping

## Requirement

You can use docker, podman, rancher or any similar tool that supports running any OCI compatible containers.

## Usage

Run any of below commands:

```
docker run --rm -it docker.io/ahabid/checker-utilities:1.0 bash
# or
podman run --rm -it docker.io/ahabid/checker-utilities:1.0 bash
```
