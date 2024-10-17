# salmon-sync

This is a Github Action that syncs a folder to a Google Cloud bucket using `rclone`.
This action is only meant to work for Deephaven's documentation needs and is not intended to be general purpose.

## Parameters
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

## Example
The action can be used as a step in a workflow
Here is an example that syncs from the local path `temp/blog` to the blog section of the bucket.
```
- name: Sync to the blog
  uses: jnumainville/salmon-sync@v1
  with:
    source: temp/blog
    destination: deephaven/deephaven.io/blog
    project_number: ${{ secrets.DOCS_GOOGLE_CLOUD_PROJECT_NUMBER}}
    bucket: ${{ secrets.DOCS_GOOGLE_CLOUD_BUCKET }}
    credentials: ${{ secrets.DOCS_GOOGLE_CLOUD_CREDENTIALS }}
```
