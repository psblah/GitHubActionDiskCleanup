# GitHubActionDiskCleanup
GitHub Action Cleanup

## Example

```yaml
name: Runner Disk Cleanup (Ubuntu)
on: push

jobs:
  runner-disk-cleanup:
    runs-on: ubuntu-latest
    steps:
      # If there is a problem with this GitHub Actions, this step will fail
      - name: Free Disk Space
        uses: psblah/GitHubActionDiskCleanup@main
        with:
          google-cloud-sdk: true
          tool-cache: true
          large-packages: true
          swap-storage: true
```


## Acknowledgement

This GitHub Actions came around because I kept rewriting the same few lines of `rm -rf` code.

Here are a few sources of inspiration:
- https://github.community/t/bigger-github-hosted-runners-disk-space/17267/11
- https://github.com/apache/flink/blob/master/tools/azure-pipelines/free_disk_space.sh
- https://github.com/ShubhamTatvamasi/free-disk-space-action
- https://github.com/actions/virtual-environments/issues/2875#issuecomment-1163392159
- https://github.com/jlumbroso/free-disk-space