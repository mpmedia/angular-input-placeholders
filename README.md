angular-input-placeholders
===================

Animates input placeholders to make it look like they are being typed in realtime.

## Install
### Bower
```bash
$ bower install angular-input-placeholders
```
Then simply just include the JavaScript file in your document!

## Usage
To use this Angular module, simply add `wb.inputPholders` as a dependency in your Angular module
```js
angular.module('yourApp', [..., 'wb.inputPholders']);
```
Then, to actually use it;
```html
<input type="text" input-pholders="Your first placeholder!|Your second placeholder.|And so on...">
```
or
```html
<input type="text" data-input-pholders="Your first placeholder!|Your second placeholder.|And so on...">
```
### Configuration
The default config values are:
- *waitBeforeDeleteMs* - 2000 ms

 The amount of milliseconds to wait before starting to delete the placeholder (the amount of time the placeholder is fully readable).
- *waitInBetweenMs* - 300 ms

  Amount of milliseconds to wait before starting to print the next placeholder.

- *writeSpeedMs* - 100 ms

  The absolute slowest speed to wait between printing characters (characters are printed at random intervals that span from 0 ms to whatever this config value is set to).

- *deleteSpeedMs* - 60 ms

  Same as `writeSpeedMs` (see above), but for when deleting characters.


####There are 2 ways of changing these config values.

You can change these configuration values either specifically for just one element, or across the whole application.

To change these values for just one element, you can do like this;
```html
<input type="text"
  input-pholders="Lorem Ipsum.."
  input-pholders-wait-before-deleting="1000"
  input-pholders-wait-in-between="50"
  input-pholders-write-speed="30"
  input-pholders-delete-speed="10" />
```

To change the default config values permanently, you can utilize the `inputPholdersProvider` in an Angular config-block, like so;
```js
angular.module('yourApp',  [..., 'wb.inputPholders'])
  // Immediately after registering your Angular module, change the config values.
  .config(function (inputPholdersProvider) {
    inputPholdersProvider.config.waitBeforeDeleteMs = 1000;
    inputPholdersProvider.config.waitInBetweenMs = 500;
    inputPholdersProvider.config.writeSpeedMs = 120;
    inputPholdersProvider.config.deleteSpeedMs = 80;
  });
```


## License
Licensed under the MIT license.

## Authors
**William Boman** <william@redwill.se>