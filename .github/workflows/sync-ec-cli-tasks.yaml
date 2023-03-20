---
name: sync-ec-cli-tasks

on:
  workflow_dispatch:
  schedule:
    # At 09:00 UTC on Tuesday
    - cron: '0 9 * * 1-5'

jobs:
  sync-ec-cli-tasks:
    runs-on: ubuntu-latest

    steps:

    - name: Checkout tekton-catalog
      uses: actions/checkout@v3
      with:
        repository: hacbs-contract/tekton-catalog
        ref: main
        path: tekton-catalog

    - name: Checkout ec-cli
      uses: actions/checkout@v3
      with:
        repository: hacbs-contract/ec-cli
        ref: main
        path: ec-cli

    - name: Sync tasks
      run: ./hack/sync-ec-cli-tasks.sh ../ec-cli
      working-directory: tekton-catalog
