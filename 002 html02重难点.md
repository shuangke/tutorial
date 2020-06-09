#  a标签的用法
## attributes: 
1. **href = "address"**

  - Use this:
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

  - 锚点 href = “#idName”
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
         
# Form
## Usage
  - send GET/POST request and refresh the current page
## Attributes for Form
  1. action
  
     - defines the action to be performes when the form is submitted. Normally, the form data is sent to the web page on the          server when user clickes on the submit button.
   
  2. target
    - It determines where to display result after hitting submit button
      - "_blank" display in new window
      - "_self" display in current window
      - "_parent" dispaly in its parent layer of window
      - "_top" display in its top layer of window
   3. method
    - get vs post:
      - GET:
        - appends form-data into the URL in name/value pairs, so it's not good to send sensive data through this method
        - length of url is limited to 2048 characters
      - POST: 
        - good for sending sensive and huge length of data through this method, because the sending form-data won't be    appended to url 
        
   4. autocomplete
      - autocomplete = "on" will give user suggestions about their userInfo, when they are filling the form
      - autocomplete = "off"
    
  ```html
    <form action="./server.php" method="POST" autocomplete="on" target="_blank">
      <input type= "text" name="userName">User Name:
    </form>
  ```   
 ## Elements in form
  - **input**
    - types:
      1. text
      2. color
      3. password
      4. file
        ```html
        <input type="file"/> <!--can only uplaod single file-->
        <imput type="file" multiple/> <!--can upload muitiple files-->
       ```
      5. radio (buttons in the same group must have the same name)
       ```html
        <input type="radio" name="gender"/> Male
        <imput type="radio" name="gender"/> Female
       ```
      6. checkbox (buttons in the same group must have the same name)
        ```html
        <input type="checkbox" name="hobbies"/> Sing
        <imput type="checkbox" name="hobbies"/> Dance
        <imput type="checkbox" name="hobbies"/> Writing
        ```
      7. hidden
         used not for user, it's used for browser to fill some data into the specific area
         Scenario: 
            broswer autimatically extracts the user id from url and fill into the form, users don't need to fill and see its id. 
            
 - **textarea**(by default user can resize the textarea by drag its right bottom corner)
   - creating no resizable textarea
      ```html
      <texarea style="resize:none; width: 50%; height=300px;"></textarea>
      ```
 - **select**
   ```html
    <select>
      <option value="">---please choose--</option>
      <option value="1">Monday</option>
      <option value="2">Tuesday</option>
    </select>  
   ```
 - **important**
    - **button vs type="submit"**
      ```html
      <button type="btton">Click Me<img src="./dog.png" alt="a dog"/></button> <!--button can contains other tags-->
      <input type="submit" value="Submit!"/><!--submit cannot contain any other tag-->
      ```
    - **every form must contain one submit function button**
  
    - **if there is only one <button> in the form and <button> does not define the type, then it will autimatically perform as a submit button**
      ```html
      <button type="submit">click</button>
      ```
    - **each input field must contain name attribute, otherwise when user click submit button the data for that field won't be sent**


    
               
               
      
    

         
         


  
