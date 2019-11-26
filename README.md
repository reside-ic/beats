## Instructions and configuration for getting beats set up

Clone this repository somewhere

```
https://github.com/reside-ic/beats
```

Install `filebeat`

```
./scripts/provision
```

Register the elastic password, using the vault

```
./scripts/register_password
```

Start the service

```
./scripts/
```

### Troubleshooting

See the [filebeat docs](https://www.elastic.co/guide/en/beats/filebeat/current/troubleshooting.html)

Most useful is to start the filebeat in blocking mode with output to console:

```
sudo filebeat -e -d "publish"
```

which should show the connection status to elastic search.
