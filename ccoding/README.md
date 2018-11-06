Dockerfile for C development

includes man, gcc, valgrind

## Build

```
docker build -t rnsloan/ccoding .
```

## Usage

Mount the current directory at `/home/code` and enter at a bash prompt

```
docker run -it --name ccoding -v $(pwd -P):/home/code -w /home/code rnsloan/ccoding /bin/bash
```

To restart

```
docker start -a -i ccoding
```
