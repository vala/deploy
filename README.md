# Deploy

This is a small ruby utility to deploy Rails apps to a git remote repo and to a
heroku app.

It allows you to easily batch execute several `git` and `heroku` commands in
a single one, using the various options provided.

It's kind of a dirty small bash command builder in ruby.
We use everyday, and we hope it can be useful to you too.

# Installation

Dirty install style

```bash
git clone git@github.com:vala/deploy && \
sudo mv deploy/deploy /usr/bin/deploy && \
rm -rf deploy
```

# Usage

In a git repo with a heroku app set up :

```bash
deploy # => git add . && git commit -a && push to origin master
deploy "Commit message" # => git add . && Commit && push to origin master
deploy -h "Commit message" # => Deploy to heroku too
deploy -hm "Commit message" # => Run migrations too
deploy -s -a my_app # => Seed app `my_app`
```

Read help below to find out what you can do with it

# Help

```
Usage: deploy [<options>] [<COMMIT-MESSAGE>]
    -b, --branch BRANCH              Choose remote origin branch to push to
    -a, --app APP                    Choose Heroku app to deploy to
    -h, --heroku                     Deploys code to Heroku
    -m, --migrate                    Migrates after deploy
    -c, --no-commit                  Don't try to commit, just push
    -n, --no-push                    Don't push, just deploy to Heroku
    -f, --force                      Force push to origin repo
    -p, --pull                       Pull origin remote branch before push. Exits if conflict exist
    -s, --seed                       Seed database after deploy
    -P, --promote                    Promote to Heroku pipeline downstream (ex: Staging -> Master)
    -r, --remote REMOTE              Specify which remote target you want to deploy to
        --update                     Updates the deploy script from remote git repo
```

