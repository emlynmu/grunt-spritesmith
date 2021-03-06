grunt-spritesmith
=================
Grunt library for using [spritesmith](https://github.com/Ensighten/spritesmith), a spritesheet and CSS pre-processor utility.

Synopsis
--------
[Spritesmith](https://github.com/Ensighten/spritesmith) accepts a list of images, stiches them together, and returns that image along with a coordinate map of where each image is located and its dimensions.

[Grunt](https://github.com/gruntjs/grunt/) is a node.js based CLI build tool.

[json2css](https://github.com/twolfson/json2css) converts the output from [Spritesmith](https://github.com/Ensighten/spritesmith) and generates variables and helper functions for hooking into inside of your CSS pre-processor.

When you combine all three of these, you get a grunt plugin that makes maintaining sprites a breeze.

Getting Started
---------------
Install this grunt plugin next to your project's [grunt.js gruntfile](https://github.com/gruntjs/grunt/blob/master/docs/getting_started.md) with: `npm install grunt-spritesmith`

Then add this line to your project's `grunt.js` gruntfile:

```javascript
grunt.loadNpmTasks('grunt-spritesmith');
```

Usage
-----
```js
grunt.initConfig({
  'sprite': {
    'all': {
      // Sprite files to read in
      'src': ['public/images/sprites/*.png'],

      // Location to output spritesheet
      'destImg': 'public/images/sprite.png',

      // Stylus with variables under sprite names
      'destCSS': 'public/css/sprite_positions.styl',

      // OPTIONAL: Manual override for imgPath specified in CSS
      'imgPath': '../sprite.png',

      // OPTIONAL: Specify algorithm (top-down, left-right, diagonal, alt-diagonal)
      'algorithm': 'alt-diagonal',

      // OPTIONAL: Specify engine (auto, canvas, gm)
      'engine': 'canvas',

      // OPTIONAL: Specify CSS format (inferred from destCSS' extension by default) (stylus, scss, sass, less, json)
      'cssFormat': 'json',

      // OPTIONAL: Specify img options
      'imgOpts': {
         // Format of the image (inferred from destImg' extension by default) (jpg, png)
         'format': 'png',

         // Quality of image (gm only)
         'quality': 90
      }
    }
  }
});
```

Contributing
------------
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint via [grunt](https://github.com/gruntjs/grunt/) and test via `npm test`.

### Algorithms
Algorithms are maintained via [twolfson/layout](https://github.com/twolfson/layout). If you would like to add one, please submit it via a pull request.

### Engines and image options
Engines and image options are maintained via [Ensighten/spritesmith](https://github.com/Ensighten/spritesmith). If you would like to add one, please submit it via a pull request.

### CSS formats
CSS formats are maintained via [twolfson/json2css](https://github.com/twolfson/json2css). If you would like to add one, please submit it via a pull request.

License
-------
Copyright (c) 2012 Ensighten
Licensed under the MIT license.