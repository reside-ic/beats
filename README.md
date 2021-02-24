# beats

Setup for running [Beats] in Docker to ship logs from other containers on the same host

## Set up

```shell
cat >.env <<EOF
BEATS_VERSION=7.11.1
BEATS_ENABLED="filebeat journalbeat"
EOF
```
You only need to enable the relevant beat(s):

- `filebeat` if you're using the default Docker logging driver (i.e. `json-file`)
- `journalbeat` for the `journald` driver - in which case you'll also need a filter on `syslog.identifier`
  e.g. `echo SYSLOG_IDENTIFIER=montagu >>.env`

## Run

1. Log into Vault
1. `./beats`
