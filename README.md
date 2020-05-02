# GitHub Actions in Action

https://lab.github.com/githubtraining/github-actions:-hello-world

https://github.com/xgqfrms/hello-github-actions/issues/1

https://github.com/xgqfrms/hello-github-actions/issues/3

## .github/workflows

1. main.yml

```yml
name: A workflow for my Hello World file
on: push

jobs:
  build:
    name: Hello world action
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v1
      - uses: ./action-a
        with:
          MY_NAME: "Mona"


```



## action

1. Dockerfile

https://github.com/xgqfrms/hello-github-actions/new/xgqfrms-patch-1?filename=action-a/Dockerfile

```Dockerfile
FROM debian:9.5-slim

ADD entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

```

2. action.yml

https://github.com/xgqfrms/hello-github-actions/new/xgqfrms-patch-1?filename=action-a/action.yml

```yml

name: "Hello Actions"
description: "Greet someone"
author: "octocat@github.com"

inputs:
  MY_NAME:
    description: "Who to greet"
    required: true
    default: "World"

runs:
  using: "docker"
  image: "Dockerfile"

branding:
  icon: "mic"
  color: "purple"

```

3. entrypoint.sh

https://github.com/xgqfrms/hello-github-actions/new/xgqfrms-patch-1?filename=action-a/entrypoint.sh

```sh  
#!/bin/sh -l

sh -c "echo Hello world my name is $INPUT_MY_NAME"

```





***

# demo


https://github.com/xgqfrms/hello-github-actions/tree/master/action-a

https://github.com/xgqfrms/hello-github-actions/actions



![](https://img2020.cnblogs.com/blog/740516/202005/740516-20200502144018259-24070475.png)


## create file by URL

https://github.com/xgqfrms/repo-name/new/master?filename=src/folder_name/filename

***



***


# Welcome to "Hello World" with GitHub Actions

This course will walk you through writing your first action and using it with a workflow file. 

**Ready to get started? Navigate to the first issue.**
