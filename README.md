# What is the OpenIndexMap-O-Matic?

The [OpenIndexMap-O-Matic](https://ubc-lib-geo.github.io/openindexmap-o-matic/) is a finding aid created to allow students, researchers, and other interested parties to visually and geographically navigate the University of British Columbia’s Walter C. Koerner Library map collection. It is a digital index map that displays the physical maps in the collection at the geographic location that they represent. The OpenIndexMap-O-Matic tool is also intended to be usable by other institutions and collections. For more information about how to use the OpenIndexMap-O-Matic for your collection, read “Implementation with Other Collections”.

# How to Use the OpenIndexMap-O-Matic

- Select an available map set from the home page.
- Click and drag on the map to move the tool.
- Zoom in and out by clicking the plus (+) or minus (-) buttons.
- Click on an outlined shape to see what maps are in the collection. Information about the maps in that area will be displayed below the map tool. 
- Click the “More Info” button to navigate to the catalogue listing for the map series. 
- Click the “Reset Map” button to return the tool to its default state. 
- Click on each map listing to see more detail about a particular map. 

# Why Use the OpenIndexMaps Specification?

[OpenIndexMaps](https://openindexmaps.org/) refers to both a community and a format for sharing index maps. Recognizing that each institution will use different naming conventions and attributes, a Geo4Lib Camp at Stanford University developed OpenIndexMaps from 2017 to 2021 as a solution to standardize index map creation. In addition, the group created a [GitHub repository](https://github.com/OpenIndexMaps) for institutions to share GIS [index maps](https://en.wikipedia.org/wiki/Index_map).

The UBC Library Maps and GIS team is invested in contributing to the OpenIndexMaps project in the spirit of collaboration and open data. Furthermore, the OpenIndexMaps metadata standard will allow for easier sharing and access to this data.

# Metadata Elements

This project was informed by UBC alumnus Emily Sugerman’s directed study on the Koerner Library’s map collection metadata requirements. Since the visualization tool was created to enhance findability for users instead of providing bibliographic information for the library, findings from this study were adapted to suit user needs and conform to the OpenIndexMap Specification.

**Note:** For the purpose of this tool, a distinction must be made between map sheets and map sets. A map sheet is an individual map, while a map set is a group of map sheets. Both items have unique metadata in this project.

The following table represents the metadata elements used for each map sheet. “Element”, “Used For”, “Type”, and “Description” are derived from OpenIndexMaps Specification. “OpenIndexMap-O-Matic Name” refers to the user-friendly name that is displayed within a map listing. “Example” is an example of the element.


## Basic building blocks:
- [Jekyll](https://jekyllrb.com/)
- [Mapbox GL JS](https://www.mapbox.com/mapbox-gljs)
- [Turf JS](https://turfjs.org/)

## Heavily inspired by:
- [CollectionBuilder](https://collectionbuilder.github.io/)
- [OpenIndexMaps](https://openindexmaps.org/) 

## Thanks to:
- [EvanLovely's csv_to_jekyll](https://github.com/EvanLovely/csv_to_jekyll)
- [June-Skeeter's mapbox-for-openindexmaps](https://github.com/ubc-lib-geo/mapbox-for-openindexmaps).
