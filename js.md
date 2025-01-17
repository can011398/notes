### 跳转网页的几种办法

##### 一、使用window.location对象

1. Window.location.href:

   ~~~javascript
   window.location.href='https://baidu.com';
   //直接跳转到新的URl
   ~~~

   * 解释：将 `window.location.href` 属性设置为新的 URL 会导致浏览器立即加载该 URL。它会创建一个新的 HTTP 请求，类似于用户在地址栏中输入新的 URL 并按下回车键。

2. window.location.replace():

   ~~~javascript
   window.location.replace('https://baidu.com');
   //替换当前页面，不会在历史记录中留下当前页面
   ~~~

   * 解释：使用 `window.location.replace()` 会将当前页面替换为新的页面，不会在浏览器的历史记录中添加当前页面，即用户无法通过浏览器的后退按钮回到当前页面。

3. Window.location.assign():

   ~~~javascript
   // 加载新的 URL，会在历史记录中添加当前页面
   window.location.assign('https://www.example.com');
   ~~~

   * 解释：`window.location.assign()` 会加载新的 URL，并将当前页面添加到浏览器的历史记录中，这样用户可以使用后退按钮返回当前页面。

**二、使用 `window.open()` 打开新窗口或标签页**：

```javascript
// 打开一个新的窗口或标签页
window.open('https://www.example.com', '_blank');
```

- 解释：

  - `window.open()` 方法用于打开一个新的浏览器窗口或标签页。第一个参数是要打开的 URL，第二个参数 `'_blank'` 表示在新的标签页或窗口中打开。你还可以使用其他目标参数，如 `'_self'`（在当前窗口中打开）、`'_parent'`（在父框架中打开）、`'_top'`（在最顶层框架中打开）。
  - 它还可以接受第三个参数，用于指定新窗口的特性，如大小、位置、是否显示工具栏等，例如：

  ```javascript
  window.open('https://www.example.com', '_blank', 'width=500,height=500');
  ```

**三、使用 HTML 元素的 `click` 事件**：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Jump Page</title>
</head>
<body>
    <a id="link" href="https://www.example.com">Click me</a>
    <script>
        // 获取链接元素
        var link = document.getElementById('link');
        // 模拟点击事件
        link.click();
    </script>
</body>
</html>
```

- 解释：
  - 首先，在 HTML 中创建一个链接元素 `<a>`，并为其设置 `href` 属性。
  - 然后使用 JavaScript 获取该元素，并调用 `click()` 方法触发点击事件，从而实现页面跳转。

**四、使用 `form` 元素的 `submit` 事件**：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Jump Page</title>
</head>
<body>
    <form id="myForm" action="https://www.example.com" method="get">
        <input type="submit" value="Submit">
    </form>
    <script>
        // 获取表单元素
        var form = document.getElementById('myForm');
        // 提交表单
        form.submit();
    </script>
</body>
</html>
```

- 解释：
  - 创建一个 `form` 元素，设置 `action` 属性为目标 URL 和 `method` 属性为 `get` 或 `post`。
  - 使用 JavaScript 获取该表单元素，并调用 `submit()` 方法提交表单，从而跳转到目标 URL。

**五、使用 `meta` 标签（HTML 方式，但可以通过 JavaScript 动态设置）**：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Jump Page</title>
    <meta http-equiv="refresh" content="0;url=https://www.example.com">
</head>
<body>
    <!-- 页面会在 0 秒后跳转到 https://www.example.com -->
</body>
</html>
```

- 解释：

  - 使用 `<meta>` 标签的 `http-equiv="refresh"` 属性，`content` 属性中的第一个值是延迟秒数，第二个值是要跳转的 URL。
  - 你也可以通过 JavaScript 动态设置该元素：

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Jump Page</title>
      <meta id="redirect" http-equiv="refresh">
      <script>
          // 动态设置跳转
          var meta = document.getElementById('redirect');
          meta.content = "0;url=https://www.example.com";
      </script>
  </body>
  </html>
  ```

**总结**：

- `window.location.href`、`window.location.replace()` 和 `window.location.assign()` 是最直接的方法，根据需求可以选择是否保留历史记录。
- `window.open()` 可用于打开新的窗口或标签页，并可以设置窗口的各种特性。
- 使用 HTML 元素的 `click` 或 `submit` 事件，可以模拟用户操作实现跳转。
- `meta` 标签可用于自动刷新或跳转页面，可通过 JavaScript 动态设置延迟和目标 URL。

在使用window.open时如何与html连接

**一、内联事件处理**：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Window Open Example</title>
</head>
<body>
    <button onclick="openNewWindow()">Open New Window</button>
    <script>
        function openNewWindow() {
            // 打开一个新的窗口或标签页
            window.open('https://www.example.com', '_blank');
        }
    </script>
</body>
</html>
```

**解释**：

- 在 HTML 中，我们添加了一个 `<button>` 元素，并使用 `onclick` 属性将其点击事件与 `openNewWindow()` 函数关联。
- 当用户点击该按钮时，会调用 `openNewWindow()` 函数。
- 在 `<script>` 标签中定义了 `openNewWindow()` 函数，该函数使用 `window.open()` 方法打开一个新的窗口或标签页，目标 URL 为 `https://www.example.com`，`'_blank'` 表示在新的标签页或窗口中打开。

**二、外部 JavaScript 文件**：

1. 创建一个外部的 JavaScript 文件，例如 `script.js`：

```javascript
function openNewWindow() {
    // 打开一个新的窗口或标签页
    window.open('https://www.example.com', '_blank');
}
```

1. 在 HTML 文件中引用该外部文件并调用该函数：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Window Open Example</title>
    <script src="script.js"></script>
</head>
<body>
    <button onclick="openNewWindow()">Open New Window</button>
</body>
</html>
```

**解释**：

- 首先，在外部的 `script.js` 文件中定义了 `openNewWindow()` 函数，使用 `window.open()` 打开新窗口。
- 在 HTML 文件中，使用 `<script src="script.js"></script>` 引用外部的 JavaScript 文件。
- 同样，使用 `<button>` 元素的 `onclick` 属性调用 `openNewWindow()` 函数。

**三、事件监听器方式**：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Window Open Example</title>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            var button = document.getElementById('openButton');
            if (button) {
                button.addEventListener('click', function() {
                    // 打开一个新的窗口或标签页
                    window.open('https://www.example.com', '_blank');
                });
            }
        });
    </script>
</head>
<body>
    <button id="openButton">Open New Window</button>
</body>
</html>
```

**解释**：

- 在 HTML 中，为 `<button>` 元素添加了 `id="openButton"`。
- 在 `<script>` 部分，使用 `document.addEventListener('DOMContentLoaded', function() {...})` 确保在 DOM 加载完成后执行代码。
- 使用 `document.getElementById('openButton')` 获取按钮元素。
- 为按钮添加 `click` 事件监听器，当点击按钮时，使用 `window.open()` 打开新窗口。

**四、使用 `href` 伪协议（不推荐）**：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Window Open Example</title>
</head>
<body>
    <a href="javascript:window.open('https://www.example.com', '_blank')">Open New Window</a>
</body>
</html>
```

**解释**：

- 使用 `<a>` 元素的 `href` 属性，并使用 `javascript:` 伪协议调用 `window.open()` 函数。
- 当用户点击该链接时，会执行 `window.open()` 函数打开新窗口。
- 这种方式不推荐，因为不符合 HTML 和 JavaScript 的分离原则，且会导致链接无法被搜索引擎索引，可能会影响页面的可访问性。

**总结**：

- 内联事件处理是一种简单的方式，但会将 HTML 和 JavaScript 混合在一起，不利于维护。
- 外部 JavaScript 文件是更好的选择，实现了代码的分离，方便管理和维护。
- 事件监听器方式是更现代和规范的做法，使用 `DOMContentLoaded` 确保在 DOM 加载完成后添加事件监听器。
- 避免使用 `href` 伪协议方式，因为其有诸多缺点。

### 如何将一张图片设为html的背景：

**一、使用 CSS 的 `background-image` 属性**：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Background Image Example</title>
    <style>
        body {
            background-image: url('image.jpg');
            background-size: cover; /* 使背景图片覆盖整个页面 */
            background-repeat: no-repeat; /* 不重复图片 */
            background-attachment: fixed; /* 固定背景图片 */
            background-position: center; /* 使图片居中 */
        }
    </style>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>This is a page with a background image.</p>
</body>
</html>
```

**解释**：

- 在 `<style>` 标签中，我们为 `body` 元素设置了 `background-image` 属性，使用 `url('image.jpg')` 指定图片的路径。
- `background-size: cover` 会使图片自动缩放，以覆盖整个页面，同时保持宽高比。
- `background-repeat: no-repeat` 确保图片不重复显示。
- `background-attachment: fixed` 会固定背景图片，使其不会随页面滚动而滚动。
- `background-position: center` 将图片定位在页面中心。

**二、使用内联 CSS**：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Background Image Example</title>
</head>
<body style="background-image: url('image.jpg'); background-size: cover; background-repeat: no-repeat; background-attachment: fixed; background-position: center;">
    <h1>Hello, World!</h1>
    <p>This is a page with a background image.</p>
</body>
</html>
```

**解释**：

- 这种方式将 CSS 样式直接写在 `body` 元素的 `style` 属性中，适用于简单的页面，但会使 HTML 代码显得冗长，不利于维护。

**三、使用 HTML 的 `<img>` 元素和 CSS 的 `position` 属性**：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Background Image Example</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
        }
        #background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1; /* 将图片置于内容之下 */
        }
    </style>
</head>
<body>
    <img id="background" src="image.jpg" alt="Background Image" style="object-fit: cover;">
    <div>
        <h1>Hello, World!</h1>
        <p>This is a page with a background image.</p>
    </div>
</body>
</html>
```

**解释**：

- 在 `<style>` 部分，将 `body` 和 `html` 的 `height` 设置为 `100%`，确保它们占据整个页面。
- 创建一个 `id` 为 `background` 的 `<img>` 元素，使用 `position: fixed` 将其固定在页面上，使其覆盖整个页面。
- `z-index: -1` 将图片置于内容之下，使内容显示在图片上方。
- `object-fit: cover` 确保图片覆盖整个元素，同时保持宽高比。

**四、使用 `background` 简写属性**：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Background Image Example</title>
    <style>
        body {
            background: url('image.jpg') no-repeat center fixed;
            background-size: cover;
        }
    </style>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>This is a page with a background image.</p>
</body>
</html>
```

**解释**：

- 使用 `background` 简写属性将多个背景属性合并，使代码更简洁。

**总结**：

- 使用 CSS 的 `background-image` 属性是最常见的方式，配合其他 `background-*` 属性可以更好地控制背景图片的显示效果。
- 内联 CSS 适合简单页面，但不利于维护。
- 使用 `<img>` 元素和 `position` 属性的方式可以实现类似的效果，但可能需要更多的布局调整。
- `background` 简写属性可以简化代码，但可能不太直观。

根据自己的需求和页面的复杂程度选择合适的方法。确保 `image.jpg` 是有效的图片路径，你可以使用相对路径或绝对路径。

### js动态

1. javascript是一种动态类型语言，这意味着变量的类型不需要指定，并且可以在程序运行中改变其类型

   例如

   ~~~javascript
   let variable=5;//变量存储了一个整数
   variable="hello";//变量存储了一个字符串
   ~~~

   在这里出现了let，let的作用与var相同都是对变量进行声明。

   以下是var和let的作用和用法

   * var 声明的变量作用是函数级或是全局级。在函数内部声明的变量var在整个函数都有效，在全局作用域声明的var变量在整个程序中都有效
   * let：声明的变量具有块级作用域，只在其所在的块级作用域内有效，如if 语句块，for循环块

   以下是区别

    ● 作用域：var声明的变量存在函数级作用域和全局作用域；let声明的变量具有块级作用域。

    ● 变量提升：var声明的变量会被提升到函数或全局作用域的顶部，即可以在声明之前使用，只是值为undefined；let声明的变量不存在变量提升，必须先声明再使用。

    ● 重复声明：var可以在同一作用域内重复声明同一个变量；let不允许在同一作用域内重复声明同一个变量。

    ● 暂时性死区：在let声明变量之前的区域为暂时性死区，在这个区域内访问该变量会报错；var不存在暂时性死区。  

