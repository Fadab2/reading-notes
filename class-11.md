## Audio, Video, and Images

### Images

#### Controlling size of images in CSS
Image sizes are controlled using the `width, height` properties. Specifies the size of the image enables the browser to laod the page faster as it will allocate a space for the image while loading the rest of the page.
Example of controlling the size of an image:
```
img {
    width: 200px;
    height: 200px;
}
```

#### Aligning images in CSS
To allign an image the `float` property is used.
To allign an image to the left the `float: left` is used. While the `float: right` is used to move the image to the right inside its conatianer.

It is good practice to give the image a class name that matches its allignment when you create an image such as align-left.
Example:

 ```
img.align - left {
    float: left;
}
img.align - right {
    float: right;
}
```
#### Adding background images
The `background-image` property is used to set an image as a background. The path to the iamge is specified using `url` such as
 ```
div {
    background-image: url("image/path");
}
```
The `background-repeat` property is used to specify how or whether an image is repeated to cover the background using the 4 properties `repeat, repeat-x/y, no-repeat`.
```
background-image: repeat;
```
The `background-position` property is used to where in window the background-iamge positioned.
```
div {
    background-image: url("image/path");
    background-image: repeat;
    background-position: center top;
}
```
### Search Engine Optimization (SEO)

SEO is a way to make your site appear when users search the web for topics/products that are covered by your site. 
Providing relevant information and linking to other sites helps your site to rank high in search engines.
There are `on-page` which is providing relevant keywords on your page and `off-page` technique which is getting other website link to your website. These two technique helps a website to rank better.
### Video and Audio APIs
HTML uses the `<video>` and `<audio>` elements to embed videos and audios.
Example:
```
<video controls>
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
</video>
```
The `controls` attribute enables playback controls on the video. Without specifying controls the video might just show as an image.

#### References:

- JAVASCRIPT & JQUERY by Jon Duckett
- HTML&CSS by Jon Duckett
  [This MDN article on audio and video elements](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)


[go to home](README.md) 

