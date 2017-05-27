## What
Phaser 2.6.2 docs in a Vuepress theme. Data scraped from existing docs with [Artoo](http://medialab.github.io/artoo/).

## How
Property scraper:
```js
var properties = artoo.scrape('#members > dl > dt', {
    name: function(){ return $(this).find('h4').attr('id') },
	type: function(){ return $(this).find('h4 .type-signature:last-of-type').text().replace(/\s*:\s*/, '') },
    description: function(){ return $(this).next('dd').find('.description').text() }
})
```

Method parameter scraper:
```js

```

Method amalgamating scraper:
```js
var methods = artoo.scrape('#methods > dl > dt', {
    name: function(){ return $(this).find('h4').attr('id') },
    signature: function(){ return $(this).find('h4 .signature').text().replace('(', '').replace(')', '').split(/,\s?/) },
    description: function(){ return $(this).next('dd').find('.description').text() }//,
    //parameters: function(){ return $(this) }
})
```
