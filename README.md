# beats

Assuming you have some Docker containers that you want to ship the logs from:

1. Log into Vault
2. `echo 'BEATS_ENABLED="filebeat journalbeat"' >.env`
3. `./beats.sh`

Notes:
- You only need to include relevant beat(s) in `BEATS_ENABLED`:
  - `filebeat` if you're using the default Docker logging driver (i.e. `json-file`)
  - `journalbeat` for the `journald` driver - in which case you'll also need a filter on `syslog.identifier` e.g. `echo SYSLOG_IDENTIFIER=montagu >>.env`
- `beats.sh` can be safely re-run e.g. to update credentials from Vault
