# CSS rendering
[CSS rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path)
1. build the DOM tree by parsing html(increamentally)
2. while building the DOM tree, browser builds the CSSOM tree by fetching the entire css file(non-increamentally) and then parsing to build the tree
3. combine DOM tree and CSSOM tree to generate render tree
4. decide the layout of the page(where to put each element, the size of each element, the flow of elements)
5. paint elements
6. based on the layer of element compose the page

# 做animation的两种方法
## method1: transform
```html
<div class='demo'></div>
```
```css
.demo {
  width: 50px;
  height: 50px;
  border: 1px solid black
  transition: all 1s;
}

.demo:hover {
  transform: scale(1.5);
}
```
## method2: using keyframes
```html
<div class='demo'></div>
```
```css
.demo {
  width: 50px;
  height: 50px;
  border: 1px solid black
}

.demo:hover {
  animation: scaleBigger 1s;
}

@keyframes scaleBigger {
  from {
    transform: scale(1.5);
  }
  to {
    transform: scale(1);
  }
}
```
## multiple states of animation
```html
<body>
  <div id='demo'></div>
  <button id='button'>click</button>
</body>
```
```css
* {padding:0;margin:0;box-sizing:border-box;}

#demo {
  width: 50px;
  height: 50px;
  border: 1px solid black;
}
#demo.start {
  animation: move 3s forwards;
}
@keyframes move {
  0% {
    transform: none;
  }
  66.66% {
    transform: tanslateX(200px);
  }
  100% {
    transform: translateX(200px) translateY(100px);
  }
}
```
```javascript
button.onclick = ()=> {
  demo.classList.add('start');
}
```
## animated heart
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>JS Bin</title>
</head>
<body>
  <div id="heart">
    <div class="left"></div>
    <div class="right"></div>
    <div class="bottom"></div>
  </div>
</body>
</html>
```
```css
*{box-sizing: border-box;}
#heart{
  display: inline-block;
  margin: 100px;
  position: relative;
  animation: .5s heart infinite alternate-reverse;
  
}
@keyframes heart {
  0%{
    transform: scale(1);
  }
  100%{
    transform: scale(1.2);
  }
}

#heart>.left{
  background: red;
  width: 50px;
  height: 50px;
  position: absolute;
  transform: rotate(45deg) translateX(31px);
  bottom: 50px;
  left: -50px;
  border-radius: 50% 0 0 50%;
}
#heart>.right{
  background: red;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  position: absolute;
  transform: rotate(45deg) translateY(31px);
  bottom: 50px;
  right: -50px;
  border-radius: 50% 50% 0 0;
}
#heart>.bottom{
  background: red;
  width: 50px;
  height: 50px;
  transform: rotate(45deg);
}
```
