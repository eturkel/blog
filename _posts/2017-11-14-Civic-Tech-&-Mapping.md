---
author: Aiyani Martin and Stephen Hess
layout: post
title: Mapping & Civic Tech- Getting Started with the Basics
---

For [Delaware Innovation Week 2017](http://2017.delawareinnovationweek.com/), we teamed up with our resident Mapping Guru, [Stephen Hess](https://github.com/trescube). He gave us an awesome intro to digital mapping using JSON, and we've documented the whole tutorial. 

>This is a step-by-step tutorial easy enough for any mapping novice (or expert) to follow.

## What is Mapping?

Various technologies go into a mapping provider:

* Data
* Rendering
* Search
* Navigation

When people think of mapping, they often think of [Google Maps](https://www.google.com/maps), [Mapquest](https://www.mapquest.com/), or their personal GPS. In this workshop, we're focusing on the data and the rendering of that data. 

Some really cool examples of what mapping can do: 

* [Michelin-Starred Restaurants in NYC](https://ny.eater.com/maps/michelin-new-york-restaurants-2017)
* [Voting Opposites (by county)](https://www.washingtonpost.com/news/the-fix/wp/2016/11/15/bringing-america-together-find-the-closest-place-that-voted-the-opposite-of-where-you-live/?utm_term=.e2feaf251eba)

## Blazingly Fast Introduction to JSON

**JSON** stands for JavaScript Object Notation.  It's used for data storage and transmission. It has a low-overhead, open standard file format, and is highly compressable and human-readable (not all zeros and ones). 

A very cool aspect of JSON is it's ability to support a wide range of data types:

* booleans
* numbers
* null
* strings
* objects
* arrays


![](/images/MappingBlog/mappingExampleJSON.png)

![example](/images/MappingBlog/mappingExampleJSON2.png)

## Geo Data Formats 

There are a number of storage mechanisms for geo data--what's used to make digital maps:

* [Well-Known Text](https://en.wikipedia.org/wiki/Well-known_text)
* [Keyhole Markup Language](https://en.wikipedia.org/wiki/Keyhole_Markup_Language)
* [Esri](https://en.wikipedia.org/wiki/Esri)
    * [Shapefiles](https://en.wikipedia.org/wiki/Shapefile)
    * [Geodatabase](https://en.wikipedia.org/wiki/ArcGIS#Geodatabase)
* [GeoJSON](http://geojson.org/)

>This tutorial focuses on GeoJSON.

## Intro to GeoJSON

JSON syntax formatted for geographic features _Points_, _Lines_, and _Polygons_. 

It's defined as a series of longitude/latitude pairs. 2d description is required in GeoJSON, but 3d is optional. 

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSON.png)

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSON3D.png)

GeoJSON can also be what's called _single_ or _double_. This refers to both the Feature and FeatureCollection, as well as Point vs MultiPoint, LineString vs MultiLineString, and Polygon vs MultiPolygon. Find detailed descriptions of all of these on the [GeoJSON Offical Manual](https://tools.ietf.org/html/rfc7946), [Oracle's GeoJSON Guide](https://docs.oracle.com/database/122/ADJSN/using-GeoJSON-geographic-data.htm#ADJSN-GUID-2AD827B4-871E-4652-87F3-AC33FE7839AE), or [Leaflet's Handy Tutorial](http://leafletjs.com/examples/geojson/).

It's also important to note that GeoJSON supports straight line geometries...which means no circles or curves allowed. You can, however, give the appearance of curves by creating a series of very short lines. 

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSONLineString.png)

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSONPolygon.png)

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSONPolygonWithHoles.png)

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSONMultiLineString.png)

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSONFeatureCollection.png)

## The Magic of GeoJSON.io

[GeoJSON.io](http://geojson.io/#map=2/20.0/0.0) is a super cool open source project anyone can use to build maps for their own use. You can read a little more about it [here](http://geojson.io/about.html). 

You can use it to locate random points (helpful if you need to see some sample geoJSON:

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSON.ioRandomPoints.png)

You can also change the view layers from drawing to Satellite (you can zoom in pretty unnervingly close, too)

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSON.ioSatelliteView.png)

Now we can start actually doing things. Whatever GeoJSON you add in the right-hand toolbar will display in your map. 

Like, for example [location data for Open Data Delaware events](https://gist.github.com/trescube/7806aa37d47adc259d931c679e8fac00/revisions)

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSON.ioODDEMeetup.png)

You can also edit the attributes of a feature, either by directly changing the code, or by clicking on the desired point and editing using GeoJSON.io's UI.

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSON.ioEditing.png)

Or, if you wanted to shade in an area, you can do that, too, using data [like this](https://whosonfirst.mapzen.com/data/856/886/11/85688611.geojson) (Note that the illusion of a curve in the below example is created by just a ton of small straight lines.) 

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSON.ioStateofDE.png)

And, of course, you can change what your map layers look like. Try creating a watercolor effect by typing _http://tile.stamen.com/watercolor/{z}/{x}/{y}.jpg_ into the _Add map layer_ option in the _Meta_ dropdown, like this: 

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSON.ioChangingLayers.png)

## Getting Started with Leaflet and Mapzen.js

**Leaflet** is "an open-source JavaScript library for mobile-friendly interactive maps." 

The **Mapzen JavaScript SDK** provides access to [Mapzen](https://mapzen.com/) services with a small wrapper around Leaflet. 

Using this combination, you can create interactive maps, like this one about DE Schools.

![](https://github.com/OpenDataDE/blog/tree/gh-pages/images/MappingBlog/mappingGeoJSON.ioLeafletAndMapzen.png)

>We're going to learn how to build this step-by-step.

### Step 1: Set Up Your Code Base

Visit [this GitHub page](https://github.com/trescube/delaware_schools) and click on the [index.html](https://github.com/trescube/delaware_schools/blob/master/index.html) link. Copy all contents of this file into a local file and save. Open the local index.html in a web browser. 

This is the completed map as we learned to build in this workshop. It shows all schools in Delaware in 2016. Notice the state is highlighted in sections of counties and each point (or school) is clickable with information contained in a pop-up window. 

So how is it done?



