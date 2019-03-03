## Week 3

### Animations
* A-Frame attaching an <a-animation> element as a child of the entity to animate.
* to define a 5-meter orbit on an entity about the Y-axis that takes 10 seconds, we can offset its position and animate the rotation of a parent entity. This animation starts with the initial rotation about the Y-axis of 0 degrees and goes around to 360 degrees. It’s defined with a duration of 10000 milliseconds, maintains the final value on each cycle of the animation, and loops indefinitely.

```html
<a-entity>
  <a-entity position="5 0 0"></a-entity>
  <a-animation attribute="rotation"
               dur="10000"
               fill="forwards"
               to="0 360 0"
               repeat="indefinite"></a-animation>
</a-entity>
```
![animation attributes](../img/animationatt.png)

```html
<a-box src=”#boxTexture” position=”0 0.5 0″ color=”blue” material=’opacity: 0.8;’>

<a-animation attribute=”position” to=”5 0 0″ direction=”alternate” dur=”3000″

repeat=”indefinite”></a-animation>

</a-box>
```
