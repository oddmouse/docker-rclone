# Rclone Beta Docker Image

This Docker image builds the latest beta from the [rclone master brach](https://github.com/ncw/rclone), is based on [Alpine Linux](https://alpinelinux.org/
) and includes the [fuse library](https://github.com/libfuse/libfuse) for mounting.

## Documentation

Visit http://rclone.org for detailed usage information.

## Examples

#### Docker CLI

```
docker run -it \
    --cap-add SYS_ADMIN \
    --device /dev/fuse \
    -v /home/user/shared:/mnt/mountpoint \
    -v /home/user/.rclone.conf:/etc/rclone.conf \
    oddmouse/rclone \
    rclone mount remote:path /mnt/mountpoint
```

#### Docker Compose

```
command: rclone mount remote:path /mnt/mountpoint'
cap_add:
  - SYS_ADMIN
devices:
  - '/dev/fuse'
environment:
  RCLONE_CONFIG_PASS: '********'
volumes:
  - shared:/mnt/mountpoint
  - /home/user/.rclone.conf:/etc/rclone.conf
```
