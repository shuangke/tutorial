#  a标签的用法
## attributes: 
  1. **href = "address"**
  
    1.1 Use this:
       ```html
       <a href="//google.com">Google</a>
       ```
       instead of 
       ```html
       <a href="http://google.com"> Google</a>
       ```
       beacause:
       //google.com can automatically determine whether we should use https or http

       the procedure:
       //google.com -- > http://google.com --> http://www.google.com --> https://www.google.com
  
    1.2 锚点 href = “#idName”
       ```html
       <p id="xxx">point1</p>
       <p>point2</p>
        .
        .
        .
       <p>pointn</p>
       <a href="#xxx">jump to</a>
       ```
       click "jump to" view point will scroll to point1 
   
 2. **target**
  - _blanck (open in new window)
  - _self (open in current window, default option)
  - _parent (open in current layer's parent level window)
  - _top (open in top layer window)
  ```html
  <a href="//google.com" target="_blank">Google</a>
  ```
 3.  download（rarely used， only work for specific new browsers）
   when open the link it will autimatically download the page which the link refrence to
 ##  伪协议
 1. javascript: {some code};
   clicking the hyper link, it will execute the code inside href
   ```html
   <a href="javascript: console.log("hello");">print hello</a>
   ```
   Note：每次点击hyper link by default都会重新刷新页面，如果有一个已填信息的form，刷新后data会被清空
   
   important usage: 当想要实现点击一个a tag不会刷新滚动页面，do noting的效果
   ```html
   <a href="javascript:;">print hello</a>
   ```
   scenario:
   点击a tag， 在当前页面pop up a new dialogue box，不要刷新当前页面
    
2. email
```html
<a href="mailto:123@gmail.com">send email to 124 </a>
```
click the link will open default mail app and set recipient to 123@gmail.com

3. phone
```html
<a href="tel: 470xxxxxxxxxx">call me</a>
```

#  Table
## basic structure
```html
<table>
  <thead>
      <tr>
        <th>表头1</th>
        <th>表头2</th>
        <th>表头3</th>
      </tr>
  </thead>
  <tbody>
     <tr>
        <td>data1</td>
        <td>data2</td>
        <td>data3</td>
      </tr>
       <tr>
        <td>data4</td>
        <td>data5</td>
        <td>data6</td>
      </tr>
  </tbody>
  <tfoot>
    <tr>
        <th>1</th>
        <th>2</th>
        <th>3</th>
      </tr>
  </tfoot>
</table>  
```
### **Note:<thead>, <tbody>, <tfoot>先写谁后写谁的顺序，对于最终的渲染效果没有影响，都是头在上，身子在中间，脚在最下面
## Table style　
  1. table-layout
  
     **auto vs fixed**
     
     auto : cell length depends on the maximal width of content, then it will never cause content overflow problem
     
     fixed(rarely used): cell length depends on the width of table（manually设定的table宽度—）, 
            width of cell （manually设定的cell宽度）—and width of first row of cell. Then it might cause content overflow
     
  2. border-spacing
  3. border-collapse
  
  ```css
  table {
    table-layout: auto;
    border-spacing: 0;
    border-collapse: collapse;
    }
  ```
  
# img
## atrributes
  1. alt 当image无法正常加载时，用户界面会出现的提示，描述性性文字
  2. height, width 
  3. src
  ```html
  <img src="./img/bear.png" alt="This is a bear image" height=50%/>
  ```
  
## Events
  1. onload 当图片加载成功会出现的事件
  2. onerror 图片加载失败会出现的事件
  ```html
  <img id="xxx" src="./dog.png"/>
  ```
  ```javascript
  xxx.onload = function() {
    console.log("image upload successfully!");
  };
  xxx.onerror = function() {//当图片加载失败，print failure message，并display 404图片
    console.log("fail to upload image");
    xxx.src = "/404.png";
  }
 ```
## responsive design
1. max-width 
```css
img {
  max-width: 300px;
}
```
* case1: screen size >= 300px
         image size = 300px (可能有留白，当screen width大于300px时)
* case2: screen size < 300px
         image size = screen size
         
         
         


  
