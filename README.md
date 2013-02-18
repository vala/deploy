# Installation

Dirty install style

```bash
git clone git@github.com:vala/deploy && \
sudo mv deploy/deploy /usr/bin/deploy && \
rm -rf deploy
```

# Usage

In a git repo with heroku app set up :

```bash
deploy "Commit message" # => git add . && Commit && push to origin master
deploy -h "Commit message" # => Deploy to heroku too
deploy -h -m "Commit message" # => Run migrations too
```

# Help

```bash
Usage: deploy [options] <COMMIT-MESSAGE>|--update
    -h, --heroku                     Deploys code to heroku
    -m, --migrate                    Migrates after deploy
    -c, --no-commit                  Don't try to commit, just push
    -p, --pull                       Pull origin master before push. Exists if conflict exist
        --update                     Updates the deploy script from remote git repo
        --help                       Shows this help message
```

# Disclaimer

Don't use it ...
