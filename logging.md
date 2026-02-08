# Logging Schema

## Log Entry Structure

Every log line is a JSON object with these fields:

| Field       | Type   | Description                              |
|-------------|--------|------------------------------------------|
| `project`   | string | SCP project name (e.g. `scp-rtg-neo`, `scp-bm-pxe-dhcp-pyserver`, `scp-gateway-neo`) |
| `time`      | string | ISO 8601 timestamp (e.g. `2026-02-07T12:34:56.789Z`) |
| `hostname`  | string | Container hostname                       |
| `pid`       | number | Process ID                               |
| `level`     | string | `debug`, `info`, `warn`, or `error`      |
| `name`      | string | Logger name — `server` or `API`          |
| `message`   | string | Human-readable log message               |

When an error is logged, it is serialized into additional fields:

| Field   | Type   | Description              |
|---------|--------|--------------------------|
| `name`  | string | Error name               |
| `message` | string | Error message          |
| `stack` | string | Full stack trace         |
| `code`  | string | Error code (if present)  |

### Example

```json
{"project":"scp-gateway-neo","time":"2026-02-07T12:34:56.789Z","hostname":"scp-gateway","pid":1,"level":"info","name":"server","message":"express is listening on http://0.0.0.0:3000"}
```
