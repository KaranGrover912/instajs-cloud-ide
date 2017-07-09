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


This page has three major sections, namely, Core, Mobile and Standard. Information on each component is available in its corresponding section in the IDE. For example, the `TChart` component is found in the Core package in the Cloud IDE and so information on its usage will be found in the Core section of this page.


<aside class="notice">
  skip to your relevant section using the navigation bar on the right or scroll downwards. <!--code>meowmeowmeow</code-->
</aside>

# Core

## TVideoPlayback

```typescript
module VideoTest{
  export class TVideoTest extends Core.Forms.TForm {
    videoPlayback1: Core.VideoPlayback.TVideoPlayback;

    VideoTestCreate(sender: Core.Classes.TControl){
      //For youtube video player
      this.videoPlayback1.createVideoPlayer(Core.VideoPlayback.TVideoType.youtube, 'oxB8hFDE6GU', true); //specify video id and not entire URL
      this.videoPlayback1.fullScreen = true;
      this.videoPlayback1.videoVolume = 80;

      //For HTML5, MP4 video player
      this.videoPlayback1.createVideoPlayer(Core.VideoPlayback.TVideoType.mp4Video, 'http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4', true);
      this.videoPlayback1.fullScreen = true;
      this.videoPlayback1.videoVolume = 1;
    }
  }
}
```

The TVideoPlayback component allows for a youtube or an HTML5, MP4 video to be added to a form. The component provides the following methods and properties.

### Methods

`createVideoPlayer(type, videoId, autoplay)`

this method creates a video player component according to user defined parameters which are

Parameter | Type | Description
--------- | ------- | -----------
type | Core.VideoPlayback.TVideoType | set to `Core.VideoPlayback.youtube` for YouTube videos and `Core.VideoPlayback.mp4Video` for MP4 videos.
videoId | String | is set to video id for youtube videos and full urls for HTML5, MP4 videos.
autoplay | boolean | If set to true, videos will autoplay as soon as they are loaded.

### Properties

Property | Type | Description
--------- | ------- | -----------
allowFullscreen | false | If set to true the videoplayer will be able to go fullscreen
videoVolume | number | is set from 0 to 100 for youtube videos and from 0 to 1 for MP4 videos

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## TChart

```typescript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

# Standard

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```typescript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

# Mobile 

## Get All Kittens

```typescript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten


```typescript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```


This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

