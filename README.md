# SCP Logging Schema

A standardized JSON logging schema for SCP services. This schema is implemented across PHP, JavaScript, and Python application components to ensure consistent, structured log output.

For the full schema specification, see [logging.md](logging.md).

## Quick Reference

Every log line is a JSON object with the following fields:

| Field       | Type   | Description                              |
|-------------|--------|------------------------------------------|
| `time`      | string | ISO 8601 timestamp                       |
| `hostname`  | string | Container hostname                       |
| `pid`       | number | Process ID                               |
| `level`     | string | `debug`, `info`, `warn`, or `error`      |
| `name`      | string | Logger name                              |
| `message`   | string | Human-readable log message               |

### Example

```json
{"time":"2026-02-07T12:34:56.789Z","hostname":"scp-gateway","pid":1,"level":"info","name":"server","message":"express is listening on http://0.0.0.0:3000"}
```