alpine-volume
=============

A base image to run any storage volume for a service. 

## Build

```
docker build -t rawmind/alpine-volume:<version> .
```

## Versions

- `0.0.2` [(Dockerfile)](https://github.com/rawmind0/alpine-volume/blob/0.0.2/Dockerfile).
- `0.0.1` [(Dockerfile)](https://github.com/rawmind0/alpine-volume/blob/0.0.1/Dockerfile).

## Usage

To start-once the service volume, exec

```
docker run -t \
  -v <volume>:<mount-point> \
  -e "SERVICE_USER=root" -e "SERVICE_UID=0" \
  -e "SERVICE_GROUP=root" -e "SERVICE_GID=0" \
  -e "SERVICE_VOLUME=<mount-point>" \
  rawmind/alpine-volume:<version> .
```

These are the default value for the environment variables:
- SERVICE_USER=${SERVICE_USER:-"root"}      # User owner of the volume
- SERVICE_UID=${SERVICE_UID:-"0"}           # UID owner of the volume
- SERVICE_GROUP=${SERVICE_GROUP:-"root"}    # Group owner of the volume
- SERVICE_GID=${SERVICE_GID:-"0"}           # GID owner of the volume
- SERVICE_VOLUME=${SERVICE_VOLUME:-"/opt"}  # Volume to own and expose
