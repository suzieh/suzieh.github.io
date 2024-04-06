---
layout: page
title: my Walkable City
description: (Python) Passion project for finding walkable cities in urban MN.
img: assets/img/walkableCity.png
importance: 2
category: Seen on GitHub
github: https://github.com/suzieh/myWalkableCity
---

In this personal passion project, I use publicly-available spatial data on bike paths, public buildings, and parks (obtained from the <a href="https://gisdata.mn.gov/">MN Geospatial Commons</a>) to explore walkable, bikeable locations in the Greater Twin Cities!

The idea for this project was born from house-hunting in the Twin Cities. While considering locations, I wanted to know where I would have easy access to bike paths, parks, groceries, and medical facilities. The concept of the "15-minute city" is a popular discussion on city planning; attempting to plan such that all people live "15-minutes" walking or biking to their basic necessities.

With that, I introduce <a href="https://github.com/suzieh/myWalkableCity">myWalkableCity</a>! A Dash application (implemented in Python and <a href="https://mywalkablecity.onrender.com/">hosted on Render</a>) which attempts to visualize the overlap of various necessities in the Twin Cities, MN.


___


## myWalkableCity


First, I had a series of geometries from MN Geospatial Commons representing parks and buildings (bolded colors below). I wanted to create "buffers" which represent the walkable distance from these paths, parks, and buildings (lighter colored areas).


<div class="row justify-content-sm-center">
    <div class="col-md-auto">
        {% include figure.html path="assets/img/example_buffers.png" title="example buffers" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Buffers for Mill City Ruins Park, Guthrie Theater, West River Road Path, and Stone Arch Bridge. Buffers for paths (West River Road and Stone Arch) are 800 meters in radius, so extend 800 meters from the path. Buffers for buildings (Guthrie Theater) and parks (Mill City Ruins) are 1000 meters in radius, extending 1000 meters from the outer most edges of these parks and buildings. 
</div>


Next we can visualize all these geometries as one on the Twin Cities area. Great! But... this is a bit overwhelming and not very interactive! Also, the plot can be slow to render with so many overlapping geometries.


<div class="row justify-content-sm-center">
    <div class="col-md-auto">
        {% include figure.html path="assets/img/all_geometries_tc.png" title="All geometries in Twin Cities" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    All buffers in the Twin Cities.
</div>


A solution : (1) Combine overlapping buffers of the same type (i.e. same type of path connected to one another). (2) Create an interactive Dash application to pick and choose important features.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dashboard_preview.png" title="Dashboard" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Buffers for Mill City Ruins Park, Guthrie Theater, West River Road Path, and Stone Arch Bridge. Buffers for paths (West River Road and Stone Arch) are 800 meters in radius, so extend 800 meters from the path. Buffers for buildings (Guthrie Theater) and parks (Mill City Ruins) are 1000 meters in radius, extending 1000 meters from the outer most edges of these parks and buildings. 
</div>

And, ta-da! We have an interactive tool for finding "walkable cities."

___


## Future Directions

There are many improvements that could be made.

First, hosting on a faster platform than the free version of Render would improve usability.

Second, the plotly map could be made more interesting by introducing "hover" information that would tell you what the park name, path name, or building name is in a particular region. Would be wonderful to give some more detailed context in the visualization.

