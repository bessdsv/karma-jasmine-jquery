karma-jasmine-jquery
====================

Jasmine-jquery plugin for Jasmine in Karma

## Installation

Install the plugin from npm:

```sh
$ npm install karma-jasmine-jquery
```

## Attention
karma-jasmine-jquery has a dependency on jasmine, so you should use `karma-jasmine` as well before `karma-jasmine-jquery`. Please note the followings.
+ https://github.com/karma-runner/karma-jasmine

## Usage
karma will autoload all plugins, whose name start with `karma-`, you can import karma-jasmine-jquery plugins manually. Please refer to http://karma-runner.github.io/0.12/config/plugins.htmt for more details. 

```js
// karma.conf.js
module.exports = function(config) {
  config.set({

      frameworks: ['jasmine-jquery','jasmine']
      //...
   })
}
```

## Information
This plugin already includes jquery version 2.1.1, it is used for the plugin. 
However, in the project, you can use a version of jquery (it can be both below and above) and they will not interfere with each other. 
When writing tests using jquery $ for the project, and to use jquery 2.1.1, use a global variable jq2 (it makes sense when you want to use when writing test jquery 2 opportunities that are not available in the current version of jquery used in your project, as I). 
Example of use:

```js
// karma.conf.js
module.exports = function(config) {
  config.set({

      frameworks: ['jquery-1.3.2', 'jasmine-jquery', 'jasmine'],
      //...
   })
}

// Jasmine test example

it('test1', function() {
    $().destroyWin('window'); // jquery 1.3.2
    expect(jq2('#window')).not.toBeInDOM(); // jq2 = jquery 2.1.1
  });

```



