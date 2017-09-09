# Simple Modal
[![Build status][travis-badge]][travis-url] [![Bower dependencies][bowerdeps-badge]][bowerdeps-url] ![Version][bower-badge] ![Size][size-badge] [![Published][webcomponents-badge]][webcomponents-url]

Simple modal is a lightweight, performant, style-agnostic modal element.

<!---
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="simple-modal.html">
    <style>
      body {
        min-height: 300px
      }
      
      simple-modal {
        font-family: sans-serif;
      }
    </style>
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->
```html
<button id="button">open modal</button>

<simple-modal id="modal" title="My modal">
  My modal's content
</simple-modal>

<script>
  var button = document.querySelector('#button'),
      modal = document.querySelector('#modal');

  button.addEventListener('click', function() {
    modal.active = true;
  });
</script>
```

## Installation & usage

Install simple-modal with Bower

```sh
$ bower install simple-modal-element --save
```

Import it into the `<head>` of your page

```html
<link rel="import" href="/bower_components/simple-modal/simple-modal.html">
```

Then use it in your project, and toggle the `active` property to open/close it.

```html
<simple-modal id="modal"></simple-modal>

<script>
  // Open modal
  document.querySelector('#modal').active = true;
</script>
```

### Polyfills for cross-browser support

Simple modal relies on emerging standards, for full cross-browser support include the [Web Components Lite][webcomponents] polyfill.

```sh
bower i webcomponentsjs --save
```

```html
<script src="/bower_components/webcomponentsjs/web-components-lite.js"></script>
```


## Options

Property  | Type    | Default  | Description                                                    
--------- | ------- | -------- | ------------                                                   
`active`  | Boolean | `false`  | State of the modal, change to open/close
`title`   | String  | `''`     | Optional title to show on the modal
`noExit`  | Boolean | `false`  | Disable user closing modal (change `active` manually instead)

Properties can either be set as attributes on the element, or imperitively with Javascript

```html
<simple-modal no-exit></simple-modal>

<script>
    document.querySelector('simple-modal').title = 'My modal';
</script>
```

## Methods 

Method       | Arguments | Description                              
------------ | --------- | ------------                               
`getModal()` | `none`    | Returns the internal modal HTML element

## Styling
Simple modal is easily styleable with custom properties and CSS mixins

Property                      | Default            | Description                                   
----------------------------- | ------------------ | ------------                                  
`--simple-modal-overlay`      | `rgba(0,0,0, 0.4)` | Color of the screen overlay when modal active                         
`--simple-modal-padding`      | `40px`             | Padding inside the modal dialog               
`--simple-modal-close-size`   | `14px`             | Size of the close button                      
`--simple-modal-close-color`  | `rgba(0,0,0,0.45)` | Color of the close button                     

Apply properties on simple-modal

```css
simple-modal {
  --simple-modal-overlay: rgba(255,255,255,0.4);
}
```

Mixin                  | Description                   
---------------------- | ------------                  
`--simple-modal`       | Style the modal dialog 
`--simple-modal-title` | Style the modal title         
`--simple-modal-close` | Style the modal close button  

Apply mixins to simple-modal

```css
simple-modal {
  --simple-modal: {
    background: black;
    color: white;
  }
}
```

## Events

Event             | Description             
------------------| ------------            
`active-changed`  | Fired when the `active` property changes - active value is stored in `detail.value`

-- 

MIT © [Simpla](https://www.simpla.io)

[webcomponents]: https://github.com/webcomponents/webcomponentsjs
[webanimations]: https://github.com/web-animations/web-animations-js
[promise]: https://github.com/stefanpenner/es6-promise

[bower-badge]: https://img.shields.io/bower/v/simple-modal-element.svg
[travis-badge]: https://img.shields.io/travis/SimpleElements/simple-modal.svg
[travis-url]: https://travis-ci.org/SimpleElements/simple-modal
[bowerdeps-badge]: https://img.shields.io/gemnasium/SimpleElements/simple-modal.svg
[bowerdeps-url]: https://gemnasium.com/bower/simple-modal-element
[size-badge]: https://badges.herokuapp.com/size/github/SimpleElements/simple-modal/master/simple-modal.html?gzip=true&color=blue
[webcomponents-badge]: https://img.shields.io/badge/webcomponents.org-published-blue.svg
[webcomponents-url]: https://www.webcomponents.org/element/SimpleElements/simple-drawer
