---
type: docs
title: Docs
layout: page
---

A-Frame ships with a bunch of cool elements.

<!-- TODO: add note about position, rotation, scale, visible, opacity -->

## `<a-camera>`

A-Frame ships by default with a camera. But if you want to change the defaults, you can drop in an `<a-camera>` element.

[View source on GitHub](https://github.com/aframevr/aframe/blob/master/elements/templates/a-camera.html)

### Attributes

| Attribute Name | Description            | Type    | Default Value | Units          | Required |
|----------------|------------------------|---------|--------------:|----------------|----------|
| `fov`          | field-of-view angle    | float   | `45`          | degrees        | no       |
| `near`         | distance of near plane | float   | `1`           | meters         | no       |
| `far`          | distance of far plane  | float   | `10000`       | meters         | no       |
| `aspect`       | aspect ratio           | float   | `window.innerWidth / window.innerHeight` | degrees | no (auto-calculated if omitted) |
| `mouselook`    | mouselook controls     | boolean | `true`        | `true`/`false` | no       |
| `locomotion`   | locomotion controls    | boolean | `true`        | `true`/`false` | no       |

### Examples

Camera with a 45° Field of View and desktop mouse-look controls and WASD keyboard controls for movement:

```html
<a-camera></a-camera>
```

Same as above but with a 65° FOV:

```html
<a-camera fov="60"></a-camera>
```

Same as above but with only desktop mouse-look controls (useful for simple point-and-click experiences)

```html
<a-camera fov="60" mouselook="true" locomotion="false"></a-camera>
```


## `<a-cube>`

Cubes are simply 3D objects with a box primitive.

[View source on GitHub](https://github.com/aframevr/aframe/blob/master/elements/templates/a-cube.html)

### Attributes

| Attribute Name  | Description         | Type    | Default Value | Units                  | Required |
|-----------------|---------------------|---------|--------------:|------------------------|----------|
| `width`         | width               | float   | `5`           | meters                 | no       |
| `height`        | height              | float   | `5`           | meters                 | no       |
| `depth`         | depth               | float   | `5`           | meters                 | no       |
| `color`         | color               | string  | `gray`        | named color/hex        | no       |
| `opacity`       | opacity             | float   | `1.0`         | factor (`0.0` - `1.0`) | no       |
| `receive-light` | `true` for basic material; `false` for PBR | boolean | `true` | `true`/`false` | no |
| `transparent`   | transparent         | boolean | `true`        | `true`/`false`         | no (`true` if `opacity < 1.0 and receiveLight`) |
| `metalness`     | metalness           | float   | `0.0`         | factor (`0.0` - `1.0`) | no       |
| `roughness`     | roughness           | float   | `0.5`         | factor (`0.0` - `1.0`) | no       |
| `src`           | URL to image        | string  |               | absolute/relative URL  | no       |

### Examples

To create a simple gray 5&times;5&times;5 cube:

```html
<a-cube></a-cube>
```

Let's get fancy and create a textured cube with a small blue cube inside it:

```html
<a-cube rotation="0 45 0" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/Trefoil_knot_left.svg/2000px-Trefoil_knot_left.svg.png" opacity="0.5">
  <a-cube class="cube" rotation="0 45 0" scale="0.5 0.5 0.5" color="blue"></a-cube>
</a-cube>
```

[View examples >](https://aframevr.github.io/aframe/examples/cubes/)


## `<a-cylinder>`

Cylinders are simply 3D objects with a cylinder primitive.

[View on GitHub](https://github.com/aframevr/aframe/blob/master/elements/templates/a-cylinder.html)


### Attributes

| Attribute Name    | Description         | Type    | Default Value | Units                  | Required |
|-------------------|---------------------|---------|--------------:|------------------------|----------|
| `radius`          | radius of the cylinder at the top *and* bottom | float | `0.5` | meters | no |
| `radius-top`      | radius of the cylinder at the top | float | `0.5` | meters | no |
| `radius-bottom`   | radius of the cylinder at the bottom | float | `0.5` | meters | no |
| `height`          | height of the cylinder | float | `1` | meters  | no |
| `segments-radius` | number of segmented faces around the circumference of the cylinder | float | `36` | meters | no
| `segments-height` | number of rows of faces along the height of the cylinder | float | `4` | meters                 | no |
| `theta-start` | start angle for first segment | float | `0` | radians | no |
| `theta-length` | the central angle (theta) of the circular sector | float | `6.3` <br> (≈ 𝛑/2) | radians                 | no |
| `open-ended` | whether the ends of the cylinder are open or capped | boolean | `false` | `true` for open; `false` for capped | no |
| `color`           | color               | string  | `gray`        | named color/hex        | no       |
| `opacity`         | opacity             | float   | `1.0`         | factor (`0.0` - `1.0`) | no       |
| `receive-light`   | `true` for basic material; `false` for PBR | boolean | `true` | `true`/`false` | no |
| `transparent`     | transparent         | boolean | `true`        | `true`/`false`         | no (`true` if `opacity < 1.0 and receiveLight`) |
| `metalness`       | metalness           | float   | `0.0`         | factor (`0.0` - `1.0`) | no       |
| `roughness`       | roughness           | float   | `0.5`         | factor (`0.0` - `1.0`) | no       |
| `src`             | URL to image        | string  |               | absolute/relative URL  | no       |

### Examples

To create a simple, closed gray cylinder with a 0.5-meter radius:

```html
<a-cylinder></a-cylinder>
```

Let's get fancy and create some cool cylinders:

```html
<!-- a red hexagon -->
<a-cylinder position="-4 0 -6" rotation="90 -90 20" radius="2" segments-radius="8" color="red"></a-cylinder>

<!-- a green pipe -->
<a-cylinder position="0 0 -6" rotation="-80 15 -20" height="5" open-ended="true" color="green"></a-cylinder>

<!-- a metallic-looking blue cylinder -->
<a-cylinder position="4 0 -6" rotation="45 -45 0" radius="2" height="1" color="blue" metalness="0.9"></a-cylinder>
```

[View examples >](https://aframevr.github.io/aframe/examples/cylinders/)


## `<a-image>`

An image is a transparent plane with an image texture.

[View on GitHub](https://github.com/aframevr/aframe/blob/master/elements/templates/a-image.html)

### Attributes

| Attribute Name  | Description         | Type    | Default Value | Units                  | Required |
|-----------------|---------------------|---------|--------------:|------------------------|----------|
| `width`         | width               | float   | `2`           | meters                 | no       |
| `height`        | height              | float   | `2`           | meters                 | no       |
| `opacity`       | opacity             | float   | `1.0`         | factor (`0.0` - `1.0`) | no       |
| `src`           | URL to image        | string  |               | absolute/relative URL  | __yes__  |

### Examples

To create an image from a URL:

```html
<a-image src="https://aframevr.github.io/aframe-core/examples/_images/pano/louvre.jpg"></a-image>
```

You can also create an image from an `<img>` in the document:

```html
<a-assets>
  <img class="louvre" src="https://aframevr.github.io/aframe-core/examples/_images/pano/louvre.jpg">
</a-assets>
<a-scene>
  <a-image src=".louvre"></a-image>
</a-scene>
```

## `<a-model>`

A model is an 3D model object (`.obj`) or Collada model object (`.dae`).

[View on GitHub](https://github.com/aframevr/aframe/blob/master/elements/templates/a-model.html)

### Attributes

| Attribute Name  | Description         | Type    | Default Value | Units                       | Required |
|-----------------|---------------------|---------|--------------:|-----------------------------|----------|
| `opacity`       | opacity             | float   | `1.0`         | factor (`0.0` - `1.0`)      | no       |
| `format`        | format of model     | string  | `collada`     | format (`obj` or `collada`) | no       |
| `src`           | URL to model        | string  |               | absolute/relative URL       | __yes__  |

### Examples

To create a model from a URL:

```html
<a-model src="https://aframevr.github.io/aframe/examples/_models/tree1/tree1.dae"></a-model>
```


## `<a-plane>`

Plainly put, a plane is a flat, two-dimensional surface.

### Attributes

| Attribute Name  | Description         | Type    | Default Value | Units                  | Required |
|-----------------|---------------------|---------|--------------:|------------------------|----------|
| `width`         | width               | float   | `1`           | meters                 | no       |
| `height`        | height              | float   | `1`           | meters                 | no       |
| `color`         | color               | string  | `gray`        | named color/hex        | no       |
| `opacity`       | opacity             | float   | `1.0`         | factor (`0.0` - `1.0`) | no       |
| `receive-light` | `true` for basic material; `false` for PBR | boolean | `true` | `true`/`false` | no |
| `transparent`   | transparent         | boolean | `true`        | `true`/`false`         | no (`true` if `opacity < 1.0 and receiveLight`) |
| `metalness`     | metalness           | float   | `0.0`         | factor (`0.0` - `1.0`) | no       |
| `roughness`     | roughness           | float   | `0.5`         | factor (`0.0` - `1.0`) | no       |
| `src`           | URL to image        | string  |               | absolute/relative URL  | no       |

### Examples

To create a simple green plane:

```html
<vr-plane rotation="0 -45 10" height="10" color="green"></vr-plane>
```

## `<a-sky>`
## `<a-sphere>`
## `<a-video>`
## `<a-videosphere>`