# How to Contribute?

## Setting up for Development

After cloning the repository you'll need to install its dependencies via [bower](http://bower.io/). And this component is a bower package itself its `.bowerrc` file sets the bower directory to `../`. To keep your file structure neat you can create a dedicated component folder where you can clone this repository and install its dependencies.

```
$ mkdir polymer-components
$ cd polymer-components
$ git clone git@github.com:prtksxna/leaflet-map-component.git
$ cd leaflet-map-component
$ bower install
```

This should set up local development. You can now go back to the `polymer-components` directory, run an HTTP server and navigate to `localhost/leaflet-map-component/`. If you have Python installed the `simpleHTTPServer` should do.

```
$ cd ..
$ pwd
~/code/polymer-components
$ python -m simpleHTTPServer
```