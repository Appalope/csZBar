
# Customized ZBar Barcode Scanner Plugin for Android only

This plugin integrates with the [ZBar](http://zbar.sourceforge.net/) library,
exposing a JavaScript interface for scanning barcodes (QR Code, EAN-13/UPC-A, UPC-E, EAN-8, Code 128, Code 39, Interleaved 2 of 5, etc).

This plugin is forked from https://github.com/tjwoon/csZBar and customized to add following changes :
1) Back button on top ofthe header.
2) Scanner view with red boundary and translucent view outside.
3) "SCAN BARCODE" text below the scanner view.

## Installation

    cordova plugin add https://github.com/Appalope/csZBar.git

## API

### Scan barcode

    cloudSky.zBar.scan(params, onSuccess, onFailure)

Arguments:

- **params**: Optional parameters:

    ```javascript
    {
        camera: "front" || "back" // defaults to "back"
        flash: "on" || "off" || "auto" // defaults to "auto". See Quirks
    }
    ```

- **onSuccess**: function (s) {...} _Callback for successful scan._
- **onFailure**: function (s) {...} _Callback for cancelled scan or error._

Return:

- success('scanned bar code') _Successful scan with value of scanned code_
- error('cancelled') _If user cancelled the scan (with back button etc)_
- error('misc error message') _Misc failure_

Status:

- Android: DONE

## LICENSE [Apache 2.0](LICENSE.md)

This plugin is released under the Apache 2.0 license, but the ZBar library on which it depends (and which is distribute with this plugin) is under the LGPL license (2.1).

