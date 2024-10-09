# salmon-sync

This is a Github Action that syncs a folder to a Google Cloud bucket using `rclone`.

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
  project_number:
    required: true
    type: string
    description: 'The Google Cloud project number.'
  bucket:
    required: true
    type: string
    description: 'The Google Cloud bucket to sync to.'
  credentials:
    required: true
    type: string
    description: 'The Google Cloud credentials.'
```