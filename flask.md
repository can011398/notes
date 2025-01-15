## 装饰器

@app.route('/')是装饰器，装饰器的主要作用是增强或修改原有代码的功能，同时保持原有代码的结构与逻辑不变。

而在flask中装饰器起到至关重要的作用

* 路由映射：通过装饰器，可以指定不同的URL路径，对应不同的处理逻辑，实现不同请求的处理。
* 请求处理：可以使用装饰器来对请求进行预处理和后处理
* 权限控制：可以通过定义装饰器来实现对视图函数的权限控制。
* 缓存控制：可以使用装饰器来实现缓存功能。

## 初期阶段

我在学习flask的初期阶段，只需要了解路由映射的作用即可

百度网址https://www.baidu.com/由以下几部分组成：

#### 协议部分

https://，表示使用安全超文本传输协议，该协议对数据进行加密传输，确保用户信息安全。

#### 域名部分

www.baidu.com，是百度网站的域名。其中，baidu.com是主域名，www是子域名，用于指向具体的业务线。

#### 端口部分

一般情况下，https协议默认端口是443，在网址中通常省略不写。

#### 路径部分

网址最后的/表示根路径，代表网站的首页。如果要访问网站内的其他页面或资源，路径部分会显示具体的目录和文件名。

#### 查询参数部分

例如在搜索时，网址可能会变为https://www.baidu.com/s?q=关键词，其中?q=关键词就是查询参数部分，用于向服务器传递搜索关键词等信息。

#### 锚点部分

百度网址有时也会包含锚点部分，用于指定网页内的特定位置，如https://www.baidu.com/#section1，#section1就是锚点。

#### 在运行方面

运行时，无论是flask run还是python3 app.py都可以运行

#### 在获取信息方面

在http协议中有两种请求的方法（我知道的）

1. get
2. post

这两种方法有多重差别

1. 数据传输方式
   + get请求将数据附加在url后面，以？分隔，多个参数用&连接http://baidu.com?param1=value1&param2=vale2，数据可见且有长度限制，会有泄密风险
   + post请求将数据放在请求体里，不在URL中显示，对数据长度无限制，适合传输大量数据。泄密风险较小。

2. 用途

   + get请求常用于从服务器获取数据，如查询文章、获取用户信息等。
   + post请求常用于向服务器提交数据，如注册用户、提交表单，上传文件等。

   #### 用法示例

   ~~~python
   from flask import Flask, request
   
   app = Flask(__name__)
   
   # 处理GET请求
   @app.route('/get_data', methods=['GET'])
   def get_data():
       param1 = request.args.get('param1')
       return f'获取到的参数1为: {param1}'
   
   # 处理POST请求
   @app.route('/post_data', methods=['POST'])
   def post_data():
       param1 = request.form.get('param1')
       return f'接收到的参数1为: {param1}'
   
   if __name__ == '__main__':
       app.run(debug=True)
   ~~~

   在get_data函数中，param1=request.arg.get('param1')用于获取通过get请求传递的参数param1的值。request.args是flask中用于获取get请求参数的对象，get（’param1‘）则从该对象中提取名为param1的参数值。例如当访问http://example.com/get_data?param1=value1时，param1就会被赋值为value1。

   在post_data函数里，param1 = request.form.get('param1')用于获取通过POST请求传递的参数param1的值。request.form是Flask中用于获取POST请求中表单数据的对象，同样通过get('param1')来提取名为param1的参数值。比如在提交包含param1的表单时，就可以用这种方式获取其值。

   #### 增加网页多样化

   在我使用flask时，我发现一些ai上给我的代码无法运行，因此，我发现一些功能需要一些特殊函数来表达，因此我发现如何导入函数

   ~~~python
   from flask import Flask,render_template
   ~~~

   在这里，Flask，render_template都是我所导入的特定模块或函数；

而render_template的作用是将渲染后的模板作为http响应返回给客户端。

在我理解就是让你通过特殊路径进入后返回给你特定的html

在增加网页层次多样化，复杂化的时候

在Flask中，如果想改变GET请求视图函数的返回值，可以通过以下几种常见方法实现：

### 修改返回数据

• 直接修改：在视图函数中直接修改要返回的数据。例如返回一个包含不同信息的字典或字符串等。假设原代码如下：
@app.route('/get_info', methods=['GET'])
def get_info():
    return {'message': '原始信息'}
若要改变返回值，可修改为：
@app.route('/get_info', methods=['GET'])
def get_info():
    return {'message': '新的信息'}
• 根据条件修改：根据不同的条件返回不同的数据。比如根据用户的身份或请求参数来决定返回内容：
@app.route('/get_info', methods=['GET'])
def get_info():
    user_type = request.args.get('user_type')
    if user_type == 'admin':
        return {'message': '管理员专属信息'}
    else:
        return {'message': '普通用户信息'}
调用不同模板

如果使用render_template返回模板，可以根据条件调用不同的模板文件，以呈现不同的页面内容。示例代码如下：
@app.route('/show_page', methods=['GET'])
def show_page():
    page_type = request.args.get('page_type')
    if page_type == 'simple':
        return render_template('simple_page.html')
    else:
        return render_template('complex_page.html')
重定向

通过redirect函数重定向到其他路由，返回不同的视图函数结果。代码如下：
from flask import redirect, url_for

@app.route('/redirect_page', methods=['GET'])
def redirect_page():
    return redirect(url_for('another_view'))

@app.route('/another_view', methods=['GET'])
def another_view():
    return {'message': '重定向后的页面信息'}

### 以下是一些使用get的例子

~~~python
from flask import Flask, request, render_template

app = Flask(__name__)

@app.route('/conditional_html', methods=['GET'])
def conditional_html():
    condition = request.args.get('condition')
    if condition == 'true':
        return '<h1>满足条件的标题</h1><p>满足条件的内容</p >'
    else:
        return render_template('other_example.html')
~~~



### 以下是一些使用post的例子

~~~python
from flask import Flask, request, render_template

app = Flask(__name__)

@app.route('/post_template_example', methods=['POST'])
def post_template_example():
    data = request.form.get('data')
    return render_template('post_example.html', data=data)
~~~

# 在Flask中使用get方法通常涉及以下几个步骤：

### 导入必要的模块

首先需要导入Flask类和request对象，示例代码如下：
~~~python
from flask import Flask, request
~~~

创建一个Flask应用实例，并指定应用的名称，示例代码如下:

~~~py
app = Flask(__name__)
~~~


### 定义路由和处理函数

使用app.route()装饰器定义路由，并在处理函数中通过request.args.get()方法获取GET请求中的参数，示例代码如下：
~~~python
@app.route('/')
def index():
    # 获取名为name的参数，如果不存在则返回默认值"Guest"
    name = request.args.get('name', 'Guest')
    return f'Hello, {name}!'
~~~

启动应用

在脚本的最后，添加以下代码来启动应用：

~~~python
if __name__ == '__main__':
    app.run(debug=True)
~~~



以上示例定义了一个简单的Flask应用，它监听根路由/。当用户访问该路由时，应用会尝试从GET请求的参数中获取名为name的参数，如果参数不存在，则使用默认值Guest，并向用户返回包含用户名的问候消息。



# 在Flask中，post通常用于处理HTTP POST请求，常用于向服务器提交数据，如用户注册、登录、提交表单等场景。以下是其使用的一般步骤：

导入必要的模块

与使用get类似，首先需要导入Flask类和request对象：

~~~python
from flask import Flask, request
~~~

创建Flask应用实例

创建一个Flask应用实例，并指定应用的名称：

~~~python
app = Flask(__name__)
~~~

定义路由和处理函数

使用app.route()装饰器定义路由，并在处理函数中通过request.form.get()方法获取POST请求中的表单数据：

~~~python
@app.route('/login', methods=['POST'])
def login():
    username = request.form.get('username')
    password = request.form.get('password')
~~~

这里可以进行登录验证等操作

~~~py
if username == 'admin' and password == '123456':
        return 'Login successful!'
    else:
        return 'Login failed!'
~~~


启动应用

在脚本的最后，添加以下代码来启动应用：

~~~python
if __name__ == '__main__':
    app.run(debug=True)
~~~

上述示例定义了一个/login路由来处理POST请求。在login函数中，使用request.form.get()方法获取名为username和password的表单数据，然后进行登录验证，并根据验证结果返回相应的消息。
