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

If you've updated `demo.html` or `demo_files/` you'll have to regenerate the Github page for the repository. This is done using a flavor of [Polymer/tools](https://github.com/Polymer/tools). Clone [this fork](https://github.com/prtksxna/tools) of the Polymer tools in the `polymer-components` directory you might have [made earlier](#pre-decelopment) and checkout the `leaflet-map-component` branch.

```
$ cd ..
$ pwd
~/code/polymer-components
$ git clone git@github.com:prtksxna/tools.git
$ cd tools
$ git checkout origin/leaflet-map-component
```

Now, create a `temp` directory inside `polymer-components/` and run `tools/bin/gp.sh`, passing it the repository's owner and  component's name.

```
$ cd ..
$ mkdir temp
$ cd temp
$ ../tools/bin/gp.sh prtksxna leaflet-map-component
```

This will push an updated copy to the `gh-pages` branch.
