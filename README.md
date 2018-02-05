# Rosetta

This project codenamed Rosetta aims to define a standard API for JavaScript libraries and to abstract
the implementation of modern framework components. In other words, you could load any JavaScript
library implementing the API and use it as a component in Angular.js, React, etc. without requiring
any extra plugin other than the Rosetta proxy specific to your framework of choice. The concept is currently in very early development stage. Feedback and any other type of help is appreciated.

## Rosetta-Angularjs example

```javascript
angular.module('app', []);
RosettaAngularjs.add('app', [{Swiper}, {Tooltip}]);
```

Then in your templates you can use the libraries as Angular.js directives:

```html
<div
  class="swiper-container"
  swiper
  swiper-on-slide-change="$ctrl.onSlideChange()"
  swiper-options="{autoplay: true}">
  ...
</div>

<button
  class="btn"
  ng-click="$ctrl.tooltip.hide()"
  title="Click me"
  tooltip
  tooltip-instance="$ctrl.tooltip"
  tooltip-options="{placement: 'top'}">
  ...
</button>
```

## Roadmap

* Document the universal API for libraries to adopt
* Implement a proxy for Angular.js (in progress: https://github.com/rosettajs/angularjs)
* Implement a proxy for React
* Implement a proxy for Angular
* Implement a proxy for Vue
* Implement a proxy for Ember? Polymer?
