Image with much of the tooling required to use wasm-pack:

- built from image [rust:1.30-slim](https://hub.docker.com/_/rust/)
- [wasm-pack 0.5.1](https://rustwasm.github.io/wasm-pack/)
- [cargo-generate 0.2.0](https://crates.io/crates/cargo-generate)
- [nodejs v10.13.0 LTS](https://nodejs.org/en/)
- [yarn 1.12.1](https://yarnpkg.com/en/)
- exposing port 8080 and port 5000

Example:

```
docker run -it --name wasm -v ${PWD}/:/usr/src/ -w usr/src/ -p 8080:8080 rnsloan/wasm-pack:1.0.0 /bin/bash
```

## webpack-dev-server

When running webpack-dev-server from inside a docker container explicitly set the host to `0.0.0.0`: `webpack-dev-server --host 0.0.0.0 --port 8080`