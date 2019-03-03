## Week 2

### CREATING A 3D Enviornment
* A scene is represented by the **<a-scene>** element. The scene is the global root object, and all entities are contained within the scene.
* The scene inherits from the Entity class so it inherits all of its properties, its methods, the ability to attach components, and the behavior to wait for all of its child nodes (e.g., <a-assets> and <a-entity>) to load before kicking off the render loop.
* **<a-scene>** handles all of the three.js and WebVR boilerplate for us:
    * Set up canvas, renderer, render loop
    * Default camera and lights
    * Set up webvr-polyfill, VREffect
    * Add UI to Enter VR that calls WebVR API


### Using Text

```html
<a-text value="Hello, World!"></a-text>
```

* The **<a-text>** tags wrap the text component.
![a text attributes](../img/atext.png)

### Images

```html
<a-image src="another-image.png"></a-image>
```

* The **image primative** shows an image on a flat plane.
![a image attributes](../img/aimage.png)


### Image Primatives

```html
<html>
  <head>
    <script src="https://aframe.io/releases/0.5.0/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
      <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
      <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
      <a-sky color="#ECECEC"></a-sky>
    </a-scene>
  </body>
</html>
```

* Primitives act as a convenience layer (i.e., syntactic sugar) primarily for newcomers. Keep in mind for now that primitives are <a-entity>s under the hood that:
    * Have a semantic name (e.g., <a-box>)
    * Have a preset bundle of components with default values
    * Map or proxy HTML attributes to component data

### Textures
* Apply the texture to our box by copying the url of the image we want to use, and then pasting it as a value of the src (source) attribute. 

```html
<a-scene embedded arjs=’sourceType: webcam;’>
    <a-box src=”https://i.imgur.com/mYmmbrp.jpg” position=”0 0.5 -0.5″ color=”blue” scale=”1 0.5 1″ rotation=“0 45 0” material=’opacity: 0.9;’></a-box>
    <a-marker-camera preset=’hiro’></a-marker-camera>
</a-scene>
```

* To add a texture to a primitive model in A-Frame, add an <a-asset> entity and create an img tag with id and source parameters, and add a source parameter to the primitive entity pointing to the ID, for example: 

```html
<a-scene embedded arjs=’sourceType: webcam;’>
    <a-assets>
        <img id=”boxTexture” src=”https://i.imgur.com/mYmmbrp.jpg”>
    </a-assets>
    <a-box src=”#boxTexture” position=”0 0.5 -0.5″ color=”blue” scale=”1 0.5 1″ rotation=“0 45 0” material=’opacity: 0.9;’></a-box>
    <a-marker-camera preset=’hiro’></a-marker-camera>
</a-scene>
```

* **segments-height** attribute is used to smooth out the edges, to make the geometry rounder and less “pointy”.

![segments height](../img/segments.png)




