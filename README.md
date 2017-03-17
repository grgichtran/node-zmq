# node-zmq
ZeroMQ with node.js bindings ready for your project.
* Alpine 3.5
* Node.js 6.10.0 LTS

[![](https://images.microbadger.com/badges/image/grgichtran/node-zmq.svg)](https://microbadger.com/images/grgichtran/node-zmq "Get your own image badge on microbadger.com")

## Example Dockerfile for project
If you don't have any native dependencies, ie only depend on pure-JS `npm` modules, then my suggestion is to run `npm install` locally before running docker build (and make sure `node_modules` isn't in your `.dockerignore`) – then you don't need an `npm install` step in your `Dockerfile` and you don't need npm installed in your Docker image – so you can use one of the smaller base* images.

```
FROM grgichtran/node-zmq

WORKDIR /src
ADD . .

RUN npm install

EXPOSE 3000
CMD ["node", "index.js"]
```
