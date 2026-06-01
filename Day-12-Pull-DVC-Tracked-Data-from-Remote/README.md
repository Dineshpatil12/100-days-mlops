# Day 13: Configure DVC Remote Storage with SeaweedFS

## Objective

Configure DVC to use a SeaweedFS S3-compatible object store and push tracked data to remote storage.

## Task Performed

* Verified the existing DVC remote configuration.
* Identified incorrect bucket name and endpoint URL.
* Updated the DVC remote to use the correct SeaweedFS bucket.
* Configured the correct S3 endpoint.
* Set the remote as the default DVC remote.
* Pushed the tracked dataset to remote storage.
* Verified that the local cache and remote storage were synchronized.

## Commands Used

```bash
# Update bucket name
dvc remote modify s3 url s3://dvc-storage

# Update SeaweedFS endpoint
dvc remote modify s3 endpointurl http://localhost:8333

# Set default remote
dvc remote default s3

# Push data to remote storage
dvc push

# Verify synchronization
dvc status -c
```

## Verification

Output after push:

```bash
1 file pushed
```

Verification status:

```bash
Cache and remote 's3' are in sync.
```

## Outcome

Successfully configured DVC to use SeaweedFS as remote storage and uploaded the tracked dataset to the `dvc-storage` bucket.

