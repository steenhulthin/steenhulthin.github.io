---
layout: blogpost
title: Add a Border Around your Leaflet map
---

#Add a Border Around your Leaflet map

If you don't know what [Leaflet](http://leafletjs.com/) is and you work with GIS I encourage you to look at it. It's a lightweight javascript library for maps similar to [OpenLayers](http://openlayers.org) and [ArcGIS API for JavaScript](https://developers.arcgis.com/javascript/). This post is about one solution to one specific problem. And it's definitely not rocket science. 

##The Problem

You like border around this - like the thumbnails from [Twitter Bootstrap 3](http://getbootstrap.com). The Bootstrap thumbnail is applied to and tag with the `thumbnail` class. 

It might look like this: 

<img class="thumbnail" src="/assests/add-a-border-around-your-leaflet-map/globes.png" alt="picture in bootstrap thumbnail" />

![picture in bootstrap thumbnail](/assests/add-a-border-around-your-leaflet-map/globes.png)

But adding the `thumbnail` class to the element containing the leaflet map won't have the desired effect. 

##tl;dr

If you would like to have a border around you leaflet map do the following:

0. Wrap the html element (the tag) that contains the leaflet map in a div. 
0. Give the wrapping element a id or class
0. add this css: `{ padding: 4px; background-color: white; border: 1px solid #dddddd; border-radius: 4px; }`


