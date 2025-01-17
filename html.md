### div

在html里面，div的用法创建容器，分组内容，应用样式，及创建布局，作用是把文档分割为独立的、不同的部分，用作严格的组织工具，配合css来整体控制某一块的样式，是构建网页布局的基础。

### 引用css

在html里，有多种方法来引用css

1. 内联样式：

   ~~~html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <title>Inline CSS Example</title>
   </head>
   <body>
       <p style="color: red; font-size: 20px;">This is a paragraph with inline CSS.</p>
   </body>
   </html>
   ~~~

   这种方式直接将 CSS 样式添加到 HTML 元素的 `style` 属性中。适用于只对单个元素进行简单样式设置的情况，但不利于代码的维护和复用。

2. 内部样式表

   ~~~html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <title>Internal CSS Example</title>
       <style>
           p {
               color: blue;
               font-size: 18px;
           }
       </style>
   </head>
   <body>
       <p>This is a paragraph styled with internal CSS.</p>
   </body>
   </html>
   ~~~

   在 HTML 的 `<head>` 部分使用 `<style>` 标签定义 CSS 样式，这些样式将应用于整个 HTML 文档。对于样式较少且仅适用于当前页面的情况比较方便。

3. 外部样式表：

   是我经常使用的一种方法

   ~~~css
   p {
       color: green;
       font-size: 16px;
   }
   ~~~

   然后再去html里引用就行

   ~~~html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <title>External CSS Example</title>
       <link rel="stylesheet" href="styles.css">
   </head>
   <body>
       <p>This is a paragraph styled with external CSS.</p>
   </body>
   </html>
   ~~~

   使用 `<link>` 元素的 `rel="stylesheet"` 属性和 `href` 属性来引入外部的 CSS 文件，`href` 指向 CSS 文件的路径。这种方式最有利于代码的维护和复用，尤其在大型项目中，可以将不同的样式分别存储在不同的 CSS 文件中，方便管理和修改。

   但是在引用css文件时会出现为了方便管理而不在同一个文件夹的情况，接下来有几种办法来解决问题：

   1. 相对路径

      假设我的文件结构如下

      ~~~plaintext
      project/
      ├── html/
      │   └── index.html
      └── css/
          └── styles.css
      ~~~

      那么我引用时应当

      ~~~html
      <!DOCTYPE html>
      <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>External CSS Example</title>
          <link rel="stylesheet" href="../css/styles.css">
      </head>
      <body>
          <p>This is a paragraph styled with external CSS.</p>
      </body>
      </html>
      ~~~

      - `../` 表示上一级目录，所以 `../css/styles.css` 会先从 `html` 文件夹的上一级目录（即 `project` 目录）开始查找 `css` 文件夹，然后找到 `styles.css` 文件。

   2. 绝对路径

      假设你的网站部署在 `http://example.com`，并且 `styles.css` 的完整 URL 是 `http://example.com/css/styles.css`，你可以这样引用：

      ~~~html
      <!DOCTYPE html>
      <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>External CSS Example</title>
          <link rel="stylesheet" href="/css/styles.css">
      </head>
      <body>
          <p>This is a paragraph styled with external CSS.</p>
      </body>
      </html>
      ~~~

      - 当使用 `/` 开头时，它表示从网站的根目录开始查找，所以 `/css/styles.css` 会从 `http://example.com` 的根目录开始寻找 `css` 文件夹和 `styles.css` 文件。这种方式在实际部署时需要确保服务器的根目录设置正确。

   ### 总结

   - **相对路径**：是相对于当前 HTML 文件的位置来定位资源文件的，使用 `../` 表示上一级目录，`./` 表示当前目录，不写或直接写文件名表示当前目录下的文件。相对路径适用于开发环境，在文件结构发生改变时，需要注意调整路径。
   - **绝对路径**：是从网站的根目录开始查找资源文件，以 `/` 开头。绝对路径在部署后相对稳定，但在开发过程中，需要确保开发服务器的根目录设置与实际部署环境相符，否则可能导致文件引用失败。

   ### 快看看

   在html里，许多事情可以通过css和js来完成