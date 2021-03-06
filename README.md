# ion-slide-box-tabs

This directive extends Ionic framework V1's ion-slide-box with selectable tabs and a tab indicator that moves as the user changes slides. 

This slider was inspired by JKnorr91's *ion-slide-tabs* directive at https://github.com/JKnorr91/ion-slide-box-tabs.

I kept the styling simple so feel free to modify the CSS / SCSS as necessary for your project!

## Installation

1. Add *ionSlideBoxTabs.js* to your Ionic Project and include it in your *index.html*, eg:

  ```html
  <script src="app/ionSlideBoxTabs/slidingTabsDirective.js"></script>
  ```

2. Register the *ion-slide-box-tabs* module with your app:

  ```
  angular.module('app', ['ionic', 'ion-slide-box-tabs'])
  ```

3. Add *ionSlideBoxTabs.css* or *ionSlideBoxTabs.scss* to your project CSS or SCSS stylesheet.

## Usage

Add the *ion-slide-box-tabs* element as a wrapper around the *ion-slide-box* element.

Add names to each tab using the *slide-tab-label="label"* attribute on each slide.

Add the *on-slide-changed="$emit('slideChanged')"* attribute to the *ion-slide-box* element. 

The *ion-slide-box-tabs* directive has an *ion-content* directive built in, so there's no need to wrap this directive in one.

  ```html
    <ion-slide-box-tabs name='mySlider'>

      <ion-slide-box show-pager="false" on-slide-changed="$emit('slideChanged')">

        <ion-slide slide-tab-label="One">
          <h1>One</h1>
        </ion-slide>

        <ion-slide slide-tab-label="Two">
          <h1>Two</h1>
        </ion-slide>

        <ion-slide slide-tab-label="Three">
          <h1>Three</h1>
        </ion-slide>

      </ion-slide-box>

    </ion-slide-box-tabs>

  ```

## API

I haven't built an API yet, but it is worth noting that *ion-slide-box-tabs* automatically resizes the slider window to the height of the content area. This can be switched off by commenting out the call to getSlideHeight() and the manipulation of the div height in the scrollTopAndResize function. 
