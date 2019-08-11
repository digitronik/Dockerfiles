# Containerised mdckeckr and markdownlint
Its docker container provide two tools related to markdown checks
1. [mdcheckr](https://github.com/mike42/mdcheckr)
2. [markdownlint-cli](https://github.com/igorshubovych/markdownlint-cli)

## Create Scripts
- mdcheckr
    ```sh
    #!/bin/sh
    IMAGE=digitronik/mdchecks
    exec docker run --rm -i -v "$PWD":/home/node "$IMAGE" mdcheckr "$@"
    ```
- markdownlint
    ```sh
    #!/bin/sh
    IMAGE=digitronik/mdchecks
    exec docker run --rm -i -v "$PWD":/home/node "$IMAGE" markdownlint "$@"
    ``` 
**Note:** make executable like `chmod +x mdcheckr`

## Usages
```sh
./mdchecker <.md files or dir>
./markdownlint <.md files or dir>
```
