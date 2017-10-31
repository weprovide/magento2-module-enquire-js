# Magento2 Enquire.js

Add Enquire.js from CDN as a require.js module shim. With fallback to local version when CDN is offline.

## Installation

1. `composer require weprovide/magento2-module-enquire-js`  
will install the latest version. If you want a specific Enquire.js version you can use this:  
`composer require weprovide/magento2-module-enquire-js:<version here>`

2. Run `bin/magento setup:upgrade`

3. Run `bin/magento setup:static-content:deploy`

### Available versions

- 2.1.2

## Usage

For usage examples of enquire.js see the [enquire.js website](http://wicky.nillia.ms/enquire.js/)

```javascript
require(['enquire'], function (enquire) {
  enquire.register("screen and (max-width:1000px)", {
  
      match : function() {},      // OPTIONAL
                                  // If supplied, triggered when the media query transitions 
                                  // *from an unmatched to a matched state*
  
      unmatch : function() {},    // OPTIONAL
                                  // If supplied, triggered when the media query transitions 
                                  // *from a matched state to an unmatched state*.
                                  // Also may be called when handler is unregistered (if destroy is not available)
  
      setup : function() {},      // OPTIONAL
                                  // If supplied, triggered once immediately upon registration of the handler
  
      destroy : function() {},    // OPTIONAL
                                  // If supplied, triggered when handler is unregistered. Place cleanup code here
  
      deferSetup : true           // OPTIONAL, defaults to false
                                  // If set to true, defers execution the setup function 
                                  // until the media query is first matched. still triggered just once
  });
});
```
