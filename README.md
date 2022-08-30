# Vue-Demo

This demo was originally based off of parts #10 and #11 of [this training course](https://www.youtube.com/watch?v=YrxBCBibVo0&list=PL4cUxeGkcC9hYYGbV60Vq3IXYNfDk8At1) but I have since add more on to it. I swapped out the demo data with more complex data and made it a gallery of item instead of a simple list.

## Project setup
```
npm install
```

## Serve JSON data
This needs to be run so that the local db.json file is hosted at localhost:3000 otherwise the fetch fails
```
json-server --watch data/db.json
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
