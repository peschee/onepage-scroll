#One Page Scroll by Pete R.
Create an Apple-like one page scroll website (iPhone 5S website) with One Page Scroll plugin
Created by [Pete R.](http://www.thepetedesign.com), Founder of [BucketListly](http://www.bucketlistly.com)

[![One Page Scroll](http://www.thepetedesign.com/images/onepage_scroll_image.png "One Page Scroll")](http://www.thepetedesign.com/demos/onepage_scroll_demo.html)

## Demo
[View demo](http://www.thepetedesign.com/demos/onepage_scroll_demo.html)

## Compatibility
Modern browsers such as Chrome, Firefox, and Safari on both desktop and smartphones have been tested. IE 9+.

## Depedencies
One Page Scroll require modernizr to detect css transition support

## Basic Usage
One Page Scroll let you transform your website into a one page scroll website that allows users to scroll one page at a time. It is perfect for creating a website in which you want to present something to the viewers. For example, [Apple's iPhone 5S website](http://www.apple.com/iphone-5s/) uses the same technique.


To add this to your website, simply include the latest jQuery library together with `jquery.onepage-scroll.js`, `onepage-scroll.css` into your document's `<head>` and call the function as follows:

````html
<body>
  ...
  <div class="main">
    <section>...</section>
    <section>...</section>
    ...
  </div>
  ...
</body>
````
Container "Main" must be one level below the `body` tag in order to make it work full page. Now call the function to activate as follows:

````javascript
$(".main").onepage_scroll({
   sectionContainer: "section", // sectionContainer accepts any kind of selector in case you don't want to use section
   easing: "ease", // Easing options accepts the CSS3 easing animation such "ease", "linear", "ease-in", "ease-out", "ease-in-out", or even cubic bezier value such as "cubic-bezier(0.175, 0.885, 0.420, 1.310)"
   animationTime: 1000, // AnimationTime let you define how long each section takes to animate
   pagination: true, // You can either show or hide the pagination. Toggle true for show, false for hide.
   updateURL: false, // Toggle this true if you want the URL to be updated automatically when the user scroll to each page.
   beforeMove: function(index) {}, // This option accepts a callback function. The function will be called before the page moves.
   afterMove: function(index) {}, // This option accepts a callback function. The function will be called after the page moves.
   loop: false, // You can have the page loop back to the top/bottom when the user navigates at up/down on the first/last page.
   touchEnabled: false, // enable or disable swipe trigger
   mousewheelEnabled: false, // enable or disable mousewheel support
   keyboard: true // enable or disable keyboard nav
});
````
And that's it. Now, your website should work the same way Apple's iPhone 5S website does. You should be able to swipe up/down as well (thanks to [Eike Send](https://github.com/eikes) for his swipe events!) when viewing your website on mobile phones.

## Public Methods
You can also trigger page move programmatically as well:

### $.fn.moveUp()
This method allows you to move the page up by one. This action is equivalent to scrolling up/swiping down.

````javascript
  $(".main").moveUp();
````

### $.fn.moveDown()
This method allows you to move the page down by one. This action is equivalent to scrolling down/swiping up.

````javascript
  $(".main").moveDown();
````

### $.fn.moveTo(index)
This method allows you to move the page to page `index`.

````javascript
  $(".main").moveTo(index);
````

## Callbacks
You can use callbacks to perform actions before or after the page move.

### beforeMove(old_page_index, new_page_index)
This callback gets called before the plugin performs its move.

````javascript
  $(".main").onepage_scroll({
    beforeMove: function(old_page_index, new_page_index) {
      ...
    }
  });
````

### afterMove(old_page_index, new_page_index)
This callback gets called after the move animation was performed.

````javascript
  $(".main").onepage_scroll({
    afterMove: function(old_page_index, new_page_index) {
      ...
    }
  });
````

If you want to see more of my plugins, visit [The Pete Design](http://www.thepetedesign.com/#design), or follow me on [Twitter](http://www.twitter.com/peachananr) and [Github](http://www.github.com/peachananr).

## Other Resources
- [OnePageScroll.js: Creating an Apple’s iPhone 5S Website](http://www.onextrapixel.com/2013/09/18/onepagescroll-js-creating-an-apples-iphone-5s-website/)
- [Eike Send's jQuery Swipe Events](https://github.com/eikes/jquery.swipe-events.js)
- [CSS Easing generator by Matthew Lein](http://matthewlein.com/ceaser/)
