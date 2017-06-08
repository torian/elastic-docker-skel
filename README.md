# Elastic Stack Docker Skeleton

This repository is intended to provide a quick playground where
you can do some testing on a log shipping pipeline using filebeat,
logstash and elasticsearch

## Configuring filebeat

The configuration file `filebeat/filebeat.yml` will be mounted by
the docker compose file, and it should work out of the box with
mostly any logtype. It will ship the contents of any file that
you place on the `logs` directory, even when the container is up,
as it is mounted on the container as a volume.

## Configuring Logstash

The filter is the only part that needs some tweaking, since there
is no fit them all solutions :)

Logstash is configured (on the docker compose file) to reload it's
configuration every 60 seconds, so there is no need to bring up and
down the stack to introduce changes.

## Running the stack

```
$> docker-compose up
```

