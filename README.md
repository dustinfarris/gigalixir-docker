# gigalixir-docker

Docker image providing the Gigalixir CLI for deploying an app to Gigalixir.

https://hub.docker.com/r/dustinfarris/gigalixir/


## Using with CircleCI

Use in your `circle.yml` file, e.g.:

```yml
jobs:
  deploy:
    docker:
      - image: dustinfarris/gigalixir
    steps:
      - checkout
      - run: |
          gigalixir login -y -e "$GIGALIXIR_EMAIL" -p "$GIGALIXIR_PASSWORD"
          gigalixir git:remote myapp
          git push -f gigalixir HEAD:refs/heads/master
```
