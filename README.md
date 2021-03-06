# cleandocker

`cleandocker` is a small bash script for cleaning up stale docker things.

# Usage

Simply run the `cleandocker` script with permissions to use docker. It will, by default, do nothing. You can enable various cleanup features by adding options to your invocation.

| Option | Description |
| ------ | ----------- |
| `-f` | *kill* any running containers |
| `-c` | *remove* all non-running containers, including any it may have killed in the `-f` step. |
| `-i` | remove any *untagged* images |
| `-v` | remove any *dangling* volumes |
| `-d` | do a dry run of all actions without actually doing anything harmful |
| `-h` | Print help message |
| `-p` | Run `docker system prune` |

# Example

The following command would kill all running docker containers, then remove all stopped containers (including those killed earlier), and then remove any docker images that are untagged.

```bash
sudo ./cleandocker -fci
```

# License

`cleandocker` is released under the MIT License. Please see the `LICENSE` file for details.
