[![NPM version][npm-image]][npm-url]
[![Dependency Status][gemnasium-image]][gemnasium-url]

# disqus

Load [disqus] threads

See in the wild on the [American Scenic Byways][byways.site] website - _[source][byways.src]_.


## Installation

Install with [npm(1)](https://www.npmjs.com):

    $ npm install --save disqus-snippet

## API


Add `#disqus_thread` element where you want the thread of discus comments to be rendered.

The following [configuration variables][disqus.config] are supported:

- `shortname` - your disqus forum id - the only mandatory parameter
- `identifier` - identifier if different than URL, recommended
- `title` - page title if different from `head.title`
- `url` - cannonical page URL, recomended if page URL can have query params
- `developer` - set to 1 when loading from `localhost`


You can pass disqus paramaters using `dataset` attributes or options object.

On the page:

```HTML
  <div id="disqus_thread" data-shortname="foo" data-title="Thrursday Foo Discussion"></div>
```

In the script:

```javascript
  var disqus = require(`disqus`);
  disqus({
    title: 'Some other title',
    developer: 1
  });
```

Parameters passed to `disqus` function overwrite those set up using `data-` attributes.

If no `#disqus_thread` element is found we die silently.

## License

  MIT


[disqus]: http://disqus.com
[disqus.config]: http://help.disqus.com/customer/portal/articles/472098-javascript-configuration-variables
[byways.site]: http://scenicbyways.info/byway/2286.html
[byways.src]: https://github.com/pirxpilot/byways

[npm-image]: https://img.shields.io/npm/v/disqus-snippet.svg
[npm-url]: https://npmjs.org/package/disqus-snippet

[gemnasium-image]: https://img.shields.io/gemnasium/pirxpilot/disqus-snippet.svg
[gemnasium-url]: https://gemnasium.com/pirxpilot/disqus-snippet
