# HTML tutorial01
## HTML 是谁发明的
  - 李爵士 Tim-Berners-Lee
## 常用的表章节的标签
* h1 ~ h6(标题)
* section(章节)
* article(文章) 
* p(段落)
* header(头部， 可以用作放广告)
* footer(脚部，可用申明产权)
* main(主要内容)
* aside(旁枝内容)
* div(划分)
## 全局属性
* class
  
  <style> can reference to the element through matching class name 
```html
<div class="userInfo"> 
  <form>
    First name:<br>
    <input type="text" name="firstname">
    <br>
    Last name:<br>
    <input type="text" name="lastname">
  </form>
</div>
```
* contenteditable
  
  tag包住的区域可以供用户编辑
  ```html
  <p contenteditable> this is an area you can edit</p>
* hidden

  快速隐藏一个tag包住的区域
* id

  定义全局里不能容许由多个同样名字的id，但实际有多个id with the same name， browser并不会报错
* style

  用于定义inline style
* tabindex

  当用户无鼠标可用，对于element设置tabindex属性，可以让用户通过hit tab键选中element
  tabindex 后面接的值可以不连续
  tabindex = -1 this element won‘t get chosen under any conditions
  tabindex = 0 this element will get chosen at last
* title

  用于显示省略号隐藏的全部内容
## 常用的内容标签
* ol + li （ordered list）
* ul + li （unordered list）
* dl + dt + dd （description list， description term and description definition）
* pre （display original info format，avoiding spacing collapse）
* hr （horizontal line used to divide two regions）
* br (force to break line)
* a (reference link, clickable link)
```html
<a href="https://www.google.com target= "_blank"> Google </a>"
```
* em (emphasis in tone, surrounded text in italic)
* strong (in bold)
* code (letter font with the same width)
* quote (use for maxims, abadges and references, show no difference in display, inline element)
* quoteblock (block element)
  
