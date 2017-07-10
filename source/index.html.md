---
title: InstaJS Cloud IDE API Reference

language_tabs:
  - typescript

toc_footers:
  - <a href='http://ide.instajs.com'>go to InstaJS Cloud IDE</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---
# Introduction 
> For Example

```typescript
module sliderTest{
  export class TSliderTest extends Core.Forms.TForm{
    slider1: Core.Slider.TSlider;
    sliderTestCreate(sender: Core.Classes.TControl){
      this.slider1.items = [
        {
          url: '5lWkZ-JaEOc',    
          type: Core.Slider.Type.youtube
        }
      ];
      this.slider1.initialize();
    }
  }
```
Welcome to the online support page for the InstaJS Cloud IDE! 


this webpage may be used as API reference for various components provided by the IDE, which can be used to build complete applications using the form builder framework.


You can view code examples in the dark area to the right which are provided in TypeScript. You can access and run the following examples on the [IDE](http://ide.instajs.com) 
itself.


This page has three major sections, namely, Core, Mobile and Standard. Information on each component is available in its corresponding section in the IDE. For example, the [TChart](/#tchart) component is found in the Core package in the Cloud IDE and so information on its usage will be found in the Core section of this page.


<aside class="notice">
  skip to your relevant section using the navigation bar on the right or scroll downwards. <!--code>meowmeowmeow</code-->
</aside>

# Core

## TVideoPlayback

> `createVideoPlayer(type, videoId, autoplay)` should be called first

```typescript
module VideoTest{
  export class TVideoTest extends Core.Forms.TForm {
    videoPlayback1: Core.VideoPlayback.TVideoPlayback;

    VideoTestCreate(sender: Core.Classes.TControl){
      //For youtube video player
      var player = this.videoPlayback1;
      var type = Core.VideoPlayback.TVideoType;
      player.createVideoPlayer(type.youtube, 'oxB8hFDE6GU', true);
      player.videoPlayback1.fullScreen = true;
      player.videoPlayback1.videoVolume = 80;

      //For HTML5, MP4 video player
      var videoUrl = 'http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4';
      player.createVideoPlayer(type.mp4Video, videoUrl, true);
      player.fullScreen = true;
      player.videoVolume = 1;
    }
  }
}
```

The TVideoPlayback component allows for a youtube or an HTML5, MP4 video to be added to a form. The component provides the following methods and properties.

### Properties

Property | Type | Description
--------- | ------- | -----------
allowFullscreen | boolean | If set to true the videoplayer will be able to go fullscreen
videoVolume | number | is set from 0 to 100 for youtube videos and from 0 to 1 for MP4 videos

### Methods

`createVideoPlayer(type, videoId, autoplay)`

this method creates a video player component according to user defined parameters which are

Parameter | Type | Description
--------- | ------- | -----------
type | Core.VideoPlayback.TVideoType | set to `Core.VideoPlayback.youtube` for YouTube videos and `Core.VideoPlayback.mp4Video` for MP4 videos.
videoId | String | is set to video id for youtube videos and full urls for HTML5, MP4 videos.
autoplay | boolean | If set to true, videos will autoplay as soon as they are loaded.

<aside class="notice">
  this method must always be called first before any other properties are set. <!--code>meowmeowmeow</code-->
</aside>

## TSlider

> slider items must be assigned before `initialize()` is called 

```typescript
module sliderTest{
  export class TSliderTest extends Core.Forms.TForm{
    slider1: Core.Slider.TSlider;
  
    sliderTestCreate(sender: Core.Classes.TControl){
      this.slider1.items = [
        {
          url: '5lWkZ-JaEOc', 
          type: Core.Slider.Type.youtube,
          autoplay: true, 
          noControls: true        
        }, 
        
        {
          url: 'http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4', 
          type: Core.Slider.Type.mp4,
          autoplay: true
        },
        
        {
          url: 'https://www.w3schools.com/css/img_fjords.jpg',
          type: Core.Slider.Type.image
        }
        
      ];
      this.slider1.initialize();
      this.slider1.autoPlay = true;
    }
  }
}
```

This component allows developers to add an image and video slider element to their form(s)

### Properties

Property | Type | Description
--------- | ------- | -----------
items | Object[ ]| accepts an array of javascript objects with `url`, `type`, `autoplay` and `noControls` properties
autoPlay | boolean | If set to true the slider component will automatically change slides
type | Core.Slider.Type | is either `Core.Slider.Type.youtube`, `Core.Slider.Type.mp4` or `Core.Slider.Type.image`
currentIndex | number | can be used to jump to a certain slide in the slider

<aside class="notice">
   items must be assigned before any methods are called.
</aside>

### Methods

`initialize()`

This method creates the TSlider component in the form using the items assigned.

`start()`

Starts slider from the first slide or creates the TSlider element if `initialize()` has not been called yet.

`next()`

Goes to next slide.

`pause()`

Pauses the slider if autoPlay is enabled.

`play()`

Plays the slider if it is paused.

`prev()`

Goes to previous slide



## TFileUploader

> Relevant properties may be specified individually as follows

```typescript
module fileUploadTest{
  export class TFileUploadTest extends Core.Forms.TForm{
    fileUploader1: Core.FileUploader.TFileUploader;
    
    fileUploadTestCreate(sender: Core.Classes.TControl){
      this.fileUploader1.accept = '.html';
      this.fileUploader1.target = "www.example.com";
      this.fileUploader1.method = "POST";
      this.fileUploader1.timeout = 100000000;
      this.fileUploader1.headers = "{'X-Custom-Header' : 'value'}"; //test headers
      this.fileUploader1.formDataName = "my-attachment";
      this.fileUploader1.maxFiles = 10;
    }
  }
}
```

This component allows developers to add a file upload component to their forms with support for drop to upload.

### Properties

Property | Type | Description
--------- | ------- | -----------
accept | string | is assigned to specify the file type
target | string | specifies the server url
method | string | specifies upload method e.g: "POST", "PUT"
timeout | number | specifies timeout in milliseconds
headers | json | accepts json to specify headers
maxFiles | number | specifies the maximum number of files required
maxFileSize | number | specifies maximum file size in bytes of file to upload
localize | object | allows changes to the file upload component
noDrop | boolean | if set to true, the file uploader component will not allow drop to upload
formDataName | string | specifies the 'name' property at Content-Disposition


### Methods

No methods are required for this component

## TChart

> Documentation under review at the moment.

```typescript
const InstaJS = require('instajs');

var api = InstaJS.authorize('insta-code');
console.log("Documentation currently being updated. Please check back later.")
```

Documentation not available at the moment. Please check later

### Properties

Currently unavailable

### Method

`comingSoon(ID)`

Property | Type | Description
--------- | ------- | -----------
ID | number | the method ID

# Standard

## TStandardElement

> Documentation under review at the moment.

```typescript
const InstaJS = require('instajs');

var api = InstaJS.authorize('insta-code');
console.log("Documentation currently being updated. Please check back later.")
```

Documentation not available at the moment. Please check later

### Properties

Currently unavailable

### Method

`comingSoon(ID)`

Property | Type | Description
--------- | ------- | -----------
ID | number | the method ID

<aside class="success"> 
  Coming soon!
</aside>

## TStandardElement

> Documentation under review at the moment.

```typescript
const InstaJS = require('instajs');

var api = InstaJS.authorize('insta-code');
console.log("Documentation currently being updated. Please check back later.")
```

Documentation not available at the moment. Please check later

### Properties

Currently unavailable

### Method

`comingSoon(ID)`

Property | Type | Description
--------- | ------- | -----------
ID | number | the method ID

<aside class="success"> 
  Coming soon!
</aside>

# Mobile 

## TMobileElement

> Documentation under review at the moment.

```typescript
const InstaJS = require('instajs');

var api = InstaJS.authorize('insta-code');
console.log("Documentation currently being updated. Please check back later.")
```

Documentation not available at the moment. Please check later

### Properties

Currently unavailable

### Method

`comingSoon(ID)`

Property | Type | Description
--------- | ------- | -----------
ID | number | the method ID

<aside class="success"> 
  Coming soon!
</aside>

## TMobileElement

> Documentation under review at the moment.

```typescript
const InstaJS = require('instajs');

var api = InstaJS.authorize('insta-code');
console.log("Documentation currently being updated. Please check back later.")
```

Documentation not available at the moment. Please check later

### Properties

Currently unavailable

### Method

`comingSoon(ID)`

Property | Type | Description
--------- | ------- | -----------
ID | number | the method ID

<aside class="success"> 
  Coming soon!
</aside>

