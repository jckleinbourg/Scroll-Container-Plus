# EaselJS-ScrollContainer

![2016-05-07 18 38 56](https://cloud.githubusercontent.com/assets/5355966/15091406/45bd814c-1483-11e6-8ca8-24e80be7efeb.png)

EaselJS extension adds ScrollContainer to CreateJS.

ScrollContainer provides scroll bars and you can use as normal Container.

## Usage

1. instantiate ScrollContainer with canvas element
2. set contentSize and bounds to calculate bar size
3. add to stage
4. add object to ScrollContainer by calling `addChild`

```js
const scroll = new createjs.ScrollContainer(canvas)
scroll.setBounds(0, 0, 520, 300)
scroll.contentSize = {
  width: 1200,
  height: 960
}
stage.addChild(scroll)

const circle = new createjs.Shape()
circle.graphics.beginFill("DeepSkyBlue").drawCircle(0, 0, 50)
circle.x = 100
circle.y = 100
scroll.addChild(circle)
```

## Features

- Shows scroll bar like Windows 10
- Scroll by the mouse wheel
- Scroll by bar dragging

## Issues

- This does not clip children

# VERSION + BY JCK:

* adds option to change scroll_bar_size

* adds option to choose vertical or horizontal orientation : "vertical", "horizontal" or "none" (none remove scrollbars, useful if your content is smaller than the bounds box)

* adds touch control (drag content pane to scroll, also works with mouse)

* dissociates mouse-wheel control in case of several scoll-container on the same page

* adds 'is_moving' public property to know if the user is sliding a pane (useful to avoid clicking on elements from a pane that contains interactive elements when scrolling it)

Snippets:
```js
var scroll = new createjs.ScrollContainer(canvas, {scroll_bar_size:10, orientation:"vertical"})
```

```js
if (scroll.is_moving){
    console.log("Some punk is sliding the pane right now");
}
```
