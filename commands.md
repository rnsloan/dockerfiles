Examples using a nodejs container

Run:
`docker run -it --name <CONTAINER_NAME> -v ${PWD}:/usr/src/ -p 3000:3000 -w /usr/src/ node:13.3.0 /bin/bash`

Start:
`docker start -ai <CONTAINER_NAME>`

Attach:
`docker exec -it <CONTAINER_NAME> bash`
