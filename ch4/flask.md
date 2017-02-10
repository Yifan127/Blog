### Flask

Flask is a micro webdevelopment framework for Python.

* **What is Web Server?**

The application responsible for sending HTML to browsers is called a **Web Server**.

Browsers send http request (get, post, put, delete) to Web Server.

And Web Server reply with a http response, usually containing HTML that represents the page requested. 

![](/assets/ch4/HTTP_request_response.png)

* **Route**

Decorator **route** is used to bind a function a URL:

```python
@app.route('/')
def index():
    ...
```

By default, a route only answers **Get** requests, but that can be changed by providing **methods** argument to the route() decorator.

```python
@app.route('/', methods=['POST', 'GET'])
def index():
    if request.method == 'POST':
        ...
    else:
        ...
```
* **Static Files**

Create a folder named **static**, and store CSS and JavaScript files in this folder.

* **Rendering Template**

Create a folder named **templates**, and store all the templates in this folder.

So, the filesystem looks like this:

```
/weather_report_web0.py
/templates
    index.html
/static
    styles.css
```

Then use **render_template()** to render template.

```python
@app.route('/', methods=['POST', 'GET'])
def index():
    if request.method == 'POST':
        render_template('index.html', weather=result)
```

* **The Request Object**








