# salmon-sync

This is a Github Action that syncs a folder to a Google Cloud bucket using `rclone`.
This action is only meant to work for Deephaven's documentation needs and is not general purpose.

```
inputs:
  source:
    required: true
    type: string
    description: 'The source directory to sync.'
  destination:
    required: true
    type: string
    description: 'The destination directory to sync. Relative to the bucket.'
  credentials:
    required: true
    type: string
    description: 'The Google Cloud credentials.'
```