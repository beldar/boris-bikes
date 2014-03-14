# Boris Bikes Component
-------

This is a Web Component that uses [Polymer](http://www.polymer-project.org/) to create it and to provide a fallback in case the browser doesn't suppoer web components.

It provides a compnent that fetches the Tube Status updates with everything necessary encapsulated on one place.

You can find a working demo here: http://beldar.github.io/boris-bikes/

To know more about web components [there](http://www.html5rocks.com/en/tutorials/webcomponents/customelements/) [are](http://www.html5rocks.com/en/tutorials/webcomponents/shadowdom/) [tons](http://css-tricks.com/modular-future-web-components/) of [resources](https://www.google.co.uk/search?q=web+components) available.


# Installation

Dependencies
------------

You have to have installed [bower](http://bower.io/), and [compass](http://compass-style.org/install/). To install the first two you'll need [node](http://nodejs.org/) too.

Install
-------

Once you have all those and cloned the repo, go to the root of the project and run:

    bower install
    
That will download all the js and css dependencies of the project.

Then run:

    npm install
    
This will download all the node dependencies (including grunt)

Finally you can launch the demo running:

    grunt serve
    
You can build the project ready for production like this:

    grunt build
    
That will leave everything ready on the `/dist` folder

# How to use

There's an example/demo on the index.html of this project, but basically, you first need to include the platform.js:

    <script src="bower_components/platform/platform.js"></script>
    
Then, just below import the html of the element:

    <link rel="import" href="elements/boris-bikes.html">

Please note that this component expects the component `current-location.html` included in this repository on the same folder.
    
And finally place the element where you want it using the attributes that you need:

    <boris-bikes></boris-bikes>

The url attribute defines what url should the component go fetch the data, **since it cannot do a cross domain  request** it gets a local xml copy, you should have some backend service that fetches the information and writes it to that file, or just change the url for the url of your backend (ex. /fetchXml ).

You can also define a longitude and latitude:

    <boris-bikes longitude="-0.0733421" latitude="51.5186345"></boris-bikes>
    
Attributes summary
-----------

| Attribute | Functionality                        | Default        |
|-----------|--------------------------------------|----------------|
| latitude  | Defines the latitude to find the closest bike rack | null         |
| longitude | Defines the longitude to find the closest bike rack          | null           |
| url       | Defines the url to get the data from | livecyclehireupdates.xml |

Functionality
------------
This component by default tries to get your geolocation from the browser, otherwise you can change latitude and longitude in the input boxes
or you can also select a street from the select.