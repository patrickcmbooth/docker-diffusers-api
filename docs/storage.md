# Storage

Most URLs passed at build args or call args support special URLs, both to
store and retrieve files.

**The Storage API is new and may change without notice, please keep a
careful look in the CHANGELOG when upgrading**.

* [AWS S3](#s3)

<a name="s3"></a>
## S3

### Build Args

```Dockerfile
ARG AWS_ACCESS_KEY_ID
ARG AWS_SECRET_ACCESS_KEY
ARG AWS_DEFAULT_REGION
# Optional
ARG AWS_S3_ENDPOINT_URL
```

### Usage

In any URL where Storage is supported (e.g. dreambooth `dest_url`):

  * `s3://endpoint/bucket/path/to/file`
  * `s3:///bucket/file` (uses the default endpoint)
  * `s3:///bucket` (for `dest_url`, filename will match your output model)
  * `http+s3://...` (force http instead of https)