# How to Contribute?

## Pre-Development

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


## Development

### Updating an existing component

Make sure to update documentation if you change an existing method. Use [JSDoc](http://usejsdoc.org/about-getting-started.html) strings to add documentation.

### Adding a new element

Create a file in the root of the project, for example `leaflet-rectangle-component.html`. You could also copy an existing file to get boilerplate code. If the element is going to be a child element of `<leaflet-map>` then you'll have to add it to the `select` attribute of the `<content>` tag in `leaflet-map-component.html`. After writing the new component import it at the top of the main `leaflet-map-component.html` file like so:

```
<link rel="import" href="leaflet-rectangle-component.html">
```

Also add it to the `sources` attribute of `core-component-page` tag in `index.html` so that its documentation is generated. You must also make sure that it behaves well with the `fitToMarkersChanges` method of `<leaflet-map>`.

## Post Development
