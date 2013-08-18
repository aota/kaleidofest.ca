# Kaleido Family Festival website

## Built with Jekyll for Github Pages

### Plugins

Because this site is built to be hosted on Github Pages we [cannot use Jekyll plugins][no-plugins]. However, certain plugins are _very_ useful and worth a little extra effort.

We're using a Sitemap generator plugin `_plugins/sitemap_generator.rb`; the catch being that it must be run locally and then commited just like a static page. At some point this could be combined with other automation tasks in a delpoy script. Note that this plugin has been altered from the [original][sitemap_gen].

## Marked-up with Foundation



## Sass mixins from Bourbon.io

`sass --watch assets/sass:assets/css --style compressed`


[no-plugins]: http://jekyllrb.com/docs/plugins/
[sitemap_gen]: https://github.com/kinnetica/jekyll-plugins


## Misc

Regex for wrapping `{10 mins}` found in schedule: `\{(\d+\s\w*)\}` replace with something like `<time class="timetable-duration">\1</time>`
