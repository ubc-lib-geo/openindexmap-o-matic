
### A static site builder for collections of geoJSON map indexes

Map-o-Matic is a static site theme designed to make interactive [map indexes](https://en.wikipedia.org/wiki/Index_map) sharable online without too much hassle. 


# Basic building blocks
The main components of this project include:
- [Jekyll](https://jekyllrb.com/)
- [TailwindCSS](https://tailwindcss.com/)
- [Nord](https://www.nordtheme.com/)
- [Mapbox GL JS](https://www.mapbox.com/mapbox-gljs)

...And heavily inspired by:
- [CollectionBuilder](https://collectionbuilder.github.io/)
- [OpenIndexMaps](https://openindexmaps.org/) 

Thanks to [EvanLovely's csv_to_jekyll](https://github.com/EvanLovely/csv_to_jekyll), [crumb1le's tailwind-nord](https://github.com/crumb1e/tailwind-nord) and [June-Skeeter's mapbox-for-openindexmaps](https://github.com/ubc-lib-geo/mapbox-for-openindexmaps).

# Documentation

Required:     
- Ruby
- Jekyll
- Node.js

Steps after these are installed:    
- clone repo and `cd` into directory
- `npm install` to install required Node packages. This might take a minute.
- `bundle exec jekyll serve` will install all the required Bundler gems and serve the site locally. If you get this far – GREAT. You can now begin your local customization. 

[more on that like `_config.yml` settings, layout settings, metadata, etc.] 

- once the updates are ready, we need to build the site with `jekyll build`. This will create a new site in the `_site` directory. But wait– we're not done! 
- now we need to run `npm run deploy` to push all of the files in `_site` to the `gh-pages` branch.


