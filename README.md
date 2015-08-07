# jQuery.sdScrollMenu
A light-weight jQuery plugin to generate a dynamic menu based on `<h*>` titles within a text.

## Releases
* **v0.1** - 07/08/2015

## Requirements
`jQuery.sdScrollMenu` requires the latest version of [`jQuery`](https://jquery.com/download/).

## Demo
Follow [this JSFiddle link](https://jsfiddle.net/D4V1D/c59f3y37/) to see the plugin in action.

## Features
* supports unlimited number of titles
* highlights titles when scrolling with `.active` class

## Usage
* **HTML**

First of all, you would need to set the plugin on a large `<div>` filled with text. For exemple: 

```html
<div id="scroll-menu">
  <h1>Section 1</h1>
  <p>Lorem ipsum ...</p>
  
  <h2>Sub-section 1.1</h2>
  <p>Nullam vestibulum ...</p>
  <p>Nunc hendrerit ...</p>
  
  <h2>Sub-section 1.2</h2>
  <p>Integer feugiat ...</p>
  
  <h3>Sub-section 1.2.1</h3>
  <p>Cras porta ...</p>
  
  <h3>Sub-section 1.2.2</h3>
  <p>Aenean vestibulum ...</p>
  
  <h1>Section 2</h1>
  <p>Cras ullamcorper ...</p>
  <!-- and so on -->
</div>
```

* **CSS**
You would then need to style respectively the `.active` class and the `.active.first` class and they are the ones applies to the matching `<li>` in the menu, like so:

```CSS
.sdsm-menu li:hover {
    color: #146;
}

.sdsm-menu li.active.first{
    font-weight: bold;
    color: #a19d38;
}

.sdsm-menu li.active {
    color: #a19d38;
}
```

* **jQuery**

The syntax of `jQuery.sdScrollMenu`'s initialization is the following:
```javascript
jQuery(function($) {

    $('#scroll-menu').sdScrollMenu({
        width: 250, // integer: in px
        scrollDuration: 500, // integer: in ms
        titles: 'h3, h4, h5, h6', // string: jQuery selectors
        highlightDuration: 1000, // integer: in ms
        highlightColor: '#a19d38' // string: color
    });

});
```

## Options
Name | Type | Default | Description
------------ | ------------- | ------------- | -------------
width | integer | `250` | The width in pixel of the menu
scrollDuration | integer | `500` | The duration in `ms` of the scrolling animation when menu links are clicked
titles | string | `'h1, h2, h3, h4, h5, h6'` | The jQuery selectors from where titles will be used to build the menu. Please note that only `<h*>` tags are supported and must be increasing.
highlightDuration | integer | `1000` | The duration of the color fading out when menu links are clicked
highlightColor | string | *(none)* | The color of the title background being fade out

## Licence
Copyright (c) 2015 Steve David

Licensed under the MIT license.

