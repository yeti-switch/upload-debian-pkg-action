# upload-debian-pkg-action

## minimal example
```
jobs:
  build:
    - uses: yeti-switch/upload-debian-pkg-action@v2
      with:
        pkgs: '../*.deb'
        gpg_private_key: ${{ secrets.GPG_PRIVATE_KEY }}
        gpg_passphrase: ${{ secrets.GPG_PASSPHRASE }}
        s3_access_key_id: ${{ secrets.DEB_AWS_ACCESS_KEY_ID }}
        s3_secret_access_key: ${{ secrets.DEB_AWS_SECRET_ACCESS_KEY }}
        s3_endpoint_url: ${{ secrets.DEB_AWS_ENDPOINT }}
```

## pre-remove package and use nightly prefix

```
jobs:
  build:
    - uses: yeti-switch/upload-debian-pkg-action@v2
      with:
        pkgs: '../*.deb'
        pkgs_to_remove: 'yeti-web'
        s3_prefix: 'nightly'

        gpg_private_key: ${{ secrets.GPG_PRIVATE_KEY }}
        gpg_passphrase: ${{ secrets.GPG_PASSPHRASE }}
        s3_access_key_id: ${{ secrets.DEB_AWS_ACCESS_KEY_ID }}
        s3_secret_access_key: ${{ secrets.DEB_AWS_SECRET_ACCESS_KEY }}
        s3_endpoint_url: ${{ secrets.DEB_AWS_ENDPOINT }}
```
