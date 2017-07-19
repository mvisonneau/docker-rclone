# docker-rclone

Inspired of [tynor88/docker-rclone](https://github.com/tynor88/docker-rclone).

## Context

I created this container to use it on my Synology NAS in order to enhance my backups onto my public cloud provider.

## Usage example

```
docker run -d \
-v rclone.conf:/root/.rclone.conf \
-v /data:/data \
-e SYNC_COMMAND="rclone sync -v --delete-during --stats 15s --checkers 20 --transfers 10 /data remote:default/target" \
--name rclone \
mvisonneau/rclone
```

By default it wait 30m between each run, this can be adjusted using the `FREQUENCY` environment variable.
