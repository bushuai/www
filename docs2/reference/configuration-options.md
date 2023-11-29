---
page_class: reference
body_class: no-aside
---

# Configuration options
Nue has a hierarchical configuration system where the site-wide settings are specified in `site.yaml` file on the root directory, the application-level settings are specified in `<appdir>/app.yaml`, and page-level setting in the front matter section of a Markdown file. App settings extends/overrides the global settings and page settings extends/overrides the app settings.


## Options index
An alphabetical index of all the configuration options:

### appdir
Name of the application directory a page belongs to. For example, the root level `index.md` could set this to "home" and read the layout, data, scripts, styles, and components from that directory.

### base
The base directory where all the styles and components are loaded on the frontend. This is similar to [<base>](//developer.mozilla.org/en-US/docs/Web/HTML/Element/base) tag and allows you to deploy the project under some path such as [/@simple-blog/](/@simple-blog/), instead to a root domain like `simple-blog.nuejs.org`.

### include
By default Nue looks for a file named "main.js" and includes that automatically on your pages. You can change this with this setting. For example a value such as `['index.js']` would auto-include "index.js". See details of [JS/Typescript modules](../concepts/js-modules.html)

### bundle
Specifies files that should be bundled so that the imported dependencies are *inlined into the file itself. For example: ´bundle: [index.js]`. See [to bundle or not to bundle](../concepts/js-modules.html#unbundled).


### class
Sets the `<body :class="class">` attribute in the default HTML layout for  page-specific CSS rules.

### dist
The output directory. Default is .`dist/dev` for the development version and `.dist/prod` for the minified production version.

### content_collection
This is a directory name for a [content collection](content-collection). Setting this to "posts" makes all the Markdown pages and their metadata available as a looped array for your template files. Good for making blog/docs indexes.

### collection_name
The name of the looped variable on the content collection. By default this is the name of the directory ie. the value of the `content_collection` option.

### globals
A site-wide setting in your `site.yaml` file to define directories that are global to all your applications. The scripts, styles, and components under global directories are automatically included to all your pages. See [files and directories](files-and-directories).

### inline_css
Settinng this to `true` inlines all CSS directly into the page to make it load faster. See [performance optimization](performance-optimization).

### prefetch_global_css
Settinng this to `true` pre- fetches all global stylesheets to make the successive page load faster. This can only be enabled when `inline_css` is set to true. See [performance optimization](performance-optimization).

### page_router
Settinng this to `true` enables [client-side-navigation] for making the successive page loads feel instant.

### port
The port number of the development server. Default is 8080

### no_hotreload
Disables [hot-reloading](hot-reloading). This is enabled by default.

### no_automount
Disables automatic mounting of [reactive islands](reactive-islands). This is enabled by default.







