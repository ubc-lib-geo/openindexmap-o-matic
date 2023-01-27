# Contents
- [What is the OpenIndexMap-O-Matic?](#what-is-the-openindexmap-o-matic)
- [How to Use the OpenIndexMap-O-Matic](#how-to-use-the-openindexmap-o-matic)
- [Why Use the OpenIndexMaps Specification?](#why-use-the-openindexmaps-specification)
- [Metadata Elements](#metadata-elements)
    - [Map Sheet Metadata](#map-sheet-metadata)
    - [Map Set Metadata](#map-set-metadata)
- [Implementation with Other Collections](#implementation-with-other-collections)

# What is the OpenIndexMap-O-Matic?

The [OpenIndexMap-O-Matic](https://ubc-lib-geo.github.io/openindexmap-o-matic/) is a finding aid created to allow students, researchers, and other interested parties to visually and geographically navigate the University of British Columbia’s Walter C. Koerner Library map collection. It is a digital index map that displays the physical maps in the collection at the geographic location that they represent. The OpenIndexMap-O-Matic tool is also intended to be usable by other institutions and collections. For more information about how to use the OpenIndexMap-O-Matic for your collection, read [Implementation with Other Collections](#implementation-with-other-collections).

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

This project was informed by UBC alumnus Emily Sugerman’s directed study on the Koerner Library’s map collection metadata requirements. Since the visualization tool was created to enhance findability for users instead of providing bibliographic information for the library, findings from this study were adapted to suit user needs and conform to the OpenIndexMaps Specification.

**Note:** For the purpose of this tool, a distinction must be made between map sheets and map sets. A map sheet is an individual map, while a map set is a group of map sheets. Both items have unique metadata in this project.

## Map Sheet Metadata

The following table represents the metadata elements used for each map sheet. “Element”, “Used For”, “Type”, and “Description” are derived from [OpenIndexMaps Specification](https://openindexmaps.org/specification/1.0.0). “OpenIndexMap-O-Matic Name” refers to the user-friendly name that is displayed within a map listing underneath the map tool. “Example” is a representation of a possible element value, and "Required or Optional" indicates whether or not the element must be included to properly integrate with the OpenIndexMap-O-Matic.

| Element | OpenIndexMap-O-Matic Name | Used For | Type | Description | Example | Required or Optional |
| --- | --- | --- | --- | --- | --- | --- |
| available | Ready to Use | Available | boolean | Indication if the institution holds the item at this location in any format | true | Optional |
| label | Map Sheet Number | Sheet/frame no. | string | Alphanumeric code identifying the sheet or frame. The value of this field is used as a tool tip in GeoBlacklight. | 093H12 | Required |
| labelAlt | Alternate Map Sheet Number | Alternate sheet/frame no. | string | Alphanumeric code for the sheet or frame that was used for previous or subsequent editions, or for when there are multiple labels | NW8 | Optional |
| lcCallNo | LC Call Number | LC Call Number | string | Library of Congress call number | G6930 s250 .L3 | Optional |
| location | Location | Location | array[String] | Geographic place name identifying the area covered by the map sheet or air photo frame | [“British Columbia”] | Optional |
| title | Title | Sheet name | string | Title of map, usually a geographic location on that sheet | Eagle Lake | Required |
| edition | Edition | Edition | string | Statement indicating the edition of the map sheet | 1 ase | Optional |
| datePub | Date Published | Publication date | string | The date that the sheet or frame was published or made available | 1961 | Optional |
| scale | Scale | Scale | string | Scale statement (representative fraction plus qualifiers) of the individual sheet/frame | 1:50,000 | Optional |
| projection | Projection | Projection | string | The map’s projection, coordinate system and datum | UTM 10 | Optional |

At the time of writing, OpenIndexMaps does not provide recommendations for set- and flight-level metadata. For the purposes of this project, a simple schema is used to reference essential information.

## Map Set Metadata

| Element | OpenIndexMap-O-Matic Name | Used For | Type | Description | Example | Required or Optional |
| --- | --- | --- | --- | --- | --- | --- |
| slug | | URL slug | string | The name of the part of a URL which will point to a specific map series | canada-nts-500k | Required |
| title | | Set title | string | The title for the map set, corresponding to the catalogue title when applicable | British Columbia, National Topographic System, 1:50,000 | Required |
| scale | Scale | Scale | string | The most common scale within the map set | 1:50,000 | Optional |
| years_published | Years | Years of publication | string | The range of time in years that the map sheets within the set have been published | 1909-2011 | Optional |
| location | Location | Location | string | The geographic location of the map set | British Columbia | Optional |
| nosheets | “X” map sheets | Number of Sheets | integer | The number of map sheets within the map set | 4028 | Optional |
| infourl | More info | Information URL | string | A link to the map set on another site, such as a catalogue listing | http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=6538787 | Required |
| geojsonurl | | GeoJSON URL | string | A link to valid GeoJSON that will supply the geographic data for the map set, can be absolute or relative paths | https://ubc-lib-geo.github.io/spatial-indexes/canada_britishColumbia_50k_nts.geojson | Required |

# Implementation with Other Collections*

***Currently this project is not capable of displaying other institution’s maps. Please check back once it has reached a further state of development.**

Index maps are located in the “maps” folder under the root directory of the project files. Each index map document is stored as an individual markdown (.md) file. Because the OpenIndexMap-O-Matic uses the [Jekyll](https://jekyllrb.com/docs/) framework, each markdown file’s contents must begin and end with a series of three hyphens “---”. This will signal to Jekyll that the information should be read as YAML. These markdown files follow the metadata schema outlined in the [Map Set Metadata](#map-set-metadata) table.

To use the OpenIndexMap-O-Matic for your own institution’s geographic data, clone the OpenIndexMap-O-Matic and delete the UBC Library’s maps from the “maps” folder without removing the folder itself. Create markdown files for each of your index maps, ensuring that the file name matches your chosen URL slug element. Then, move each of your markdown files into the “maps” folder.

To create multiple index map files, you may find it easier to write in a spreadsheet editor and run a script to output each map as a markdown file. For this route, ensure that each metadata element from the table is included, along with the triple hyphens before and after the information. Another way to create the index maps is to use the template provided below. Copy these lines of code and paste them into a markdown file, or right click <a href="https://raw.githubusercontent.com/ubc-lib-geo/openindexmap-o-matic/bac4b875c9e1fa5bd005af32221997578b21b91d/template.md">this link</a> and select "Save link as...". Switch out the placeholder information after each attribute. Note that ```layout: map-item``` should remain the same.

 ```
 ---
 layout: map-item 
 slug: your-map-slug
 title: Your Map Set Title
 scale: 1:Number
 years_published: StartYear-EndYear
 location: Location
 nosheets: Number
 infourl: valid URL
 geojsonurl: valid GeoJSON URL
 ---
```

For examples of valid GeoJSON URLs, visit UBC Library’s [Spatial Indexes](https://github.com/ubc-lib-geo/spatial-indexes) repository. Check out the [OpenIndexMaps repository](https://github.com/OpenIndexMaps) for some open access spatial indexes by different institutions.

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
