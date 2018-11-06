
- built from node:4.2.1
- watchman v3.9.0
- phantomjs 2.0.0
- latest ember-cli from npm


## Example Usage

```
docker run -it --name emberjs -v ${PWD}/:/usr/src/ -w usr/src/ -p 4200:4200 -p 35729:35729 rnsloan/emberjs
```

## Credit

[https://github.com/danielra](https://github.com/danielra) for the phantomjs 2.0.0 binary
