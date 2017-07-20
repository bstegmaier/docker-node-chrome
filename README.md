# docker-node-chrome
Docker image including node and chrome for headless testing

This image adds chromium and a thin wrapper script to the official node image to facilitate headless testing with e.g. karma. Contrary to other solutions, we do not install xvfb but rather use the new headless mode in chrome, which leads to smaller images.

Just run...
```docker run --rm \
  -v "$PWD":/usr/src/app \
  -w /usr/src/app \
  -e CI=true \
  bstegmaier/node-chrome:8 \
  sh -c 'npm install; npm test'```
