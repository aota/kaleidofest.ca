# Kaleido Family Festival website

## Content Editing

Most content edits can be made via [Prose](http://prose.io). Use the [AOTA](https://github.com/aota) account.


## Built with Jekyll for Github Pages

Using the [Github Pages gem][pages-gem].

To match the live Github Pages environment, run `bundle update`. To run the Jekyll development server run `jekyll serve --watch` and load [localhost:4000](localhost:4000).

### Plugins

Because this site is built to be hosted on Github Pages we [cannot use Jekyll plugins][no-plugins]. However, certain plugins are _very_ useful and worth a little extra effort.

We're using a Sitemap generator plugin `_plugins/sitemap-generator.rb`; the catch being that it must be run locally and then commited just like a static page. At some point this could be combined with other automation tasks in a delpoy script. Note that this plugin has been altered from the [original][sitemap-gen].

## Marked-up with Foundation

[Foundation 4][foundation], to be specific.

## Sass mixins from Bourbon.io

See [Bourbon.io][bourbon]

To compile, run the following command from the root directory: `sass --watch assets/sass:assets/css --style compressed`

## Generating Map tiles

Read [this](http://macwright.org/2012/08/13/images-as-maps.html) and [this](http://build-failed.blogspot.ca/2012/11/zoomable-image-with-leaflet.html).

These are the commands to generate new map tiles. Source files not included; `df2014-map.jpg` just needs to be a big jpg (this one was 4933 by 5483 px).

```shell
python togeo.py df2014-map.jpg
gdal2tiles.py -p raster df2014-map.jpg.tif maptiles
```

## Misc

Regex for wrapping `{10 mins}` found in schedule: `\{(\d+\s\w*)\}` replace with something like `<time class="timetable-duration">\1</time>`


[no-plugins]: http://jekyllrb.com/docs/plugins/
[sitemap-gen]: https://github.com/kinnetica/jekyll-plugins
[foundation]: http://foundation.zurb.com/
[bourbon]: http://bourbon.io/docs/
[pages-gem]: https://github.com/github/pages-gem
