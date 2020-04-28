# crypt4gh-docker

This is a crypt4gh docker image. See the <https://pypi.org/project/crypt4gh/> for more reference.

## Use

Crete a folder called `data`, put there the private key, the public key, and the file to encrypt. Then run `docker`:

```
$ docker run --rm -it -v $PWD/data:/tmp/data --entrypoint sh lvarin/crypt4gh
# crypt4gh encrypt --sk /tmp/data/testcineca.sk --recipient /tmp/data/ega_key.c4gh.pub </tmp/data/lorem >/tmp/data/lorem.c4gh
```

If a permisison error is raised, it may be SELinux:

```
chcon -Rt svirt_sandbox_file_t data
```

If everything went fine, the encrypted file should be in the `data` directory.

