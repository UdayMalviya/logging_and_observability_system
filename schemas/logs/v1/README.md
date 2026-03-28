# Logs Schema v1

## Purpose
Canonical schema for logs ingestion across the observability platform.

## Required Fields

| Field   | Type  | Description |
|--------|------|-------------|
| ts     | int64 | Epoch millis |
| service| string | Service name |
| level  | enum   | Log level |
| msg    | string | Log message |

## Optional Fields

- trace_id
- span_id
- host
- env
- version
- tags
- meta

## Constraints

- Max payload size: 1MB
- Max meta keys: 50
- Max tags: 20
- Max msg length: 64KB

## Log Levels

DEBUG, INFO, WARN, ERROR, FATAL

## Versioning Rules

- Additive changes only
- Never remove fields
- Never reuse field numbers (proto)

## Notes

- `meta` is not indexed in storage
- `tags` should be low cardinality