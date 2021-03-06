# Tags and `Dockerfile` links

- [`0.10.31`, `0.10`, `0`, `latest` (*0.10/Dockerfile*)](https://github.com/docker-library/node/blob/9cb7597ec2e5e4885e29bff9b2ab0a9cfb9c6b83/0.10/Dockerfile)
- [`0.10.31-onbuild`, `0.10-onbuild`, `0-onbuild`, `onbuild` (*0.10/onbuild/Dockerfile*)](https://github.com/docker-library/node/blob/9cb7597ec2e5e4885e29bff9b2ab0a9cfb9c6b83/0.10/onbuild/Dockerfile)
- [`0.11.13`, `0.11` (*0.11/Dockerfile*)](https://github.com/docker-library/node/blob/d017d679e92e84a810c580cdb29fcdbba23c2bb9/0.11/Dockerfile)
- [`0.11.13-onbuild`, `0.11-onbuild` (*0.11/onbuild/Dockerfile*)](https://github.com/docker-library/node/blob/d017d679e92e84a810c580cdb29fcdbba23c2bb9/0.11/onbuild/Dockerfile)
- [`0.8.28`, `0.8` (*0.8/Dockerfile*)](https://github.com/docker-library/node/blob/d017d679e92e84a810c580cdb29fcdbba23c2bb9/0.8/Dockerfile)
- [`0.8.28-onbuild`, `0.8-onbuild` (*0.8/onbuild/Dockerfile*)](https://github.com/docker-library/node/blob/d017d679e92e84a810c580cdb29fcdbba23c2bb9/0.8/onbuild/Dockerfile)

# What is Node.js?
Node.js is a software platform for scalable server-side and networking applications. Node.js applications are written in JavaScript, and can be run within the Node.js runtime on Mac OS X, Windows and Linux with no changes.

Node.js applications are designed to maximize throughput and efficiency, using non-blocking I/O and asynchronous events. Node.js applications run single-threaded, although Node.js uses multiple threads for file and network events. Node.js is commonly used for real time applications due to its asynchronous nature.

Node.js internally uses the Google V8 JavaScript engine to execute code, and a large percentage of the basic modules are written in JavaScript. Node.js contains a built-in asynchronous I/O library for file, socket and HTTP communication. The HTTP and socket support allows Node.js to act as a web server without additional web server software such as Apache.

> [wikipedia.org/wiki/Node.js](https://en.wikipedia.org/wiki/Node.js)

# How to use this image

## Create a `Dockerfile` in your nodejs app project.

    FROM node:0.10.31-onbuild
    # replace this with your application's default port
    EXPOSE 8888

Then build and run the docker image.

    docker build -t my-nodejs-app
    docker run -it --rm --name my-running-app my-nodejs-app

### Notes

The image assumes that your application has a file named [`package.json`](https://www.npmjs.org/doc/json.html) listing its dependencies and defining its [start script](https://www.npmjs.org/doc/misc/npm-scripts.html#default-values).

## Run a single nodejs script

For many single file projects, it may not be convenient to write a `Dockerfile` for your project. In such cases, you can run a nodejs script by using the nodejs docker image directly.

    docker run -it --rm --name my-running-script -v "$(pwd)":/usr/src/myapp -w /usr/src/myapp node:0.10.31 node your-daemon-or-script.js

# User Feedback

## Issues

If you have any questions about the image, please contact us through a [GitHub issue](https://github.com/docker-library/node/issues) or in the IRC channel `#docker-library` on [Freenode](https://freenode.net).

## Contributing

If you want to contribute new features or updates, we are always thrilled to receive pull requests, and do our best to process them as fast as possible.

We recommend discussing your plans through a [GitHub issue](https://github.com/docker-library/node/issues) before starting to code - especially for more ambitious contributions. This gives other contributors a chance to point you in the right direction, give feedback on your design, and maybe point out if someone else is working on the same thing.
