!SLIDE the-title-slide hide-h2s

# Modernizr
## today's web &#8211; today!

!SLIDE

## about me
## Neal Lindsay
## [@neall](http://twitter.com/neall)
## 2Checkout.com

!SLIDE

# [Modernizr](http://modernizr.com)

!SLIDE

# Faruk Ateş [@KuraFire](http://twitter.com/kurafire)
# Paul Irish [@paul_irish](http://twitter.com/paul_irish)
# Alex Sexton [@SlexAxton](http://twitter.com/slexaxton)

!SLIDE

    @@@ html
    <!DOCTYPE html>
    <html class="no-js">
      <head>
        <title>My Awesome HTML5 Page</title>
        <link rel="stylesheet" href="s.css">
        <script src="modernizr.js"></script>
      </head>
      <body>
        <header>
          <h1>Hello, Internet!</h1>
        </header>
      </body>
    </html>

!SLIDE

# What does it do?

!SLIDE

# HTML5 shim
# feature detection
# asset loading

!SLIDE

!SLIDE

# HTML5 shim

!SLIDE

## new semantic elements, even in IE6

    @@@ html
    <section> <nav> <article>
     <aside> <hgroup> <time>
    <mark> <header> <footer>

!SLIDE

# includes iepp.js

!SLIDE

!SLIDE

# feature detection

!SLIDE

# html classes for CSS

!SLIDE

# before Modernizr runs

    @@@ html
    <html class="no-js">

!SLIDE

# after Modernizr runs

    @@@ html
    <html class="js flexbox canvas canvastext
    webgl no-touch geolocation postmessage
    no-websqldatabase indexeddb hashchange
    history draganddrop no-websockets rgba hsla
    multiplebgs backgroundsize borderimage
    borderradius boxshadow textshadow opacity
    no-cssanimations csscolumns cssgradients
    no-cssreflections csstransforms
    no-csstransforms3d csstransitions fontface
    generatedcontent video audio localstorage
    sessionstorage webworkers applicationcache
    svg inlinesvg smil svgclippaths">

!SLIDE

    @@@ css
    a.fallbacklink {
      display: none;
    }
    .no-js a.fallbacklink {
      display: block;
    }

!SLIDE

# `Modernizr.featurename`
# for JavaScript

!SLIDE

    @@@ javascript
    if (Modernizr.hashchange) {
      window.onhashchange = hashHandler;
    } else {
      var manualHashChecker = function() {
        // implementation left out
      };
      setInterval(manualHashChecker, 50);
    }

!SLIDE

!SLIDE

# asset loading
## (a.k.a. [yepnope.js](http://yepnopejs.com/))

!SLIDE

    @@@ javascript
    Modernizr.load({
      test: Modernizr.hashchange,
      nope: 'hashchangefaker.js'
    });

!SLIDE

    @@@ javascript
    Modernizr.load({
      test: Modernizr.history,
      yep: 'partialpageloading.js'
    });

!SLIDE

# asynchronous loading
# /
# sequential execution

!SLIDE

    @@@ javascript
    Modernizr.load({
      load: [
        'jquery.js',
        'underscore.js',
        'backbone.js',
        'script_that_uses_backbone.js'
      ],
      complete: function(){
        console && console.log('all loaded');
      }
    });

!SLIDE

!SLIDE

# caveats

!SLIDE

# don't over-detect

    @@@ css
    .fancybox {
      background: #333;
      background: rgba(0,0,0,0.5);
    }

!SLIDE

# Modernizr.load ([yepnope](http://yepnopejs.com/))
# requires proper
# JS/CSS caching

!SLIDE bullets

## fin (and resources)

* [@KuraFire](http://twitter.com/kurafire), [@paul_irish](http://twitter.com/paul_irish), [@SlexAxton](http://twitter.com/slexaxton)
* [Modernizr](http://modernizr.com/), [yepnope](http://yepnopejs.com/)
* [IE print protector](http://www.iecss.com/print-protector/)
