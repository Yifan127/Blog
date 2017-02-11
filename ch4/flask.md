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
from flask import request
from flask import render_template


@app.route('/', methods=['POST', 'GET'])
def index():
    if request.method == 'POST':
        render_template('weather.html', weather=result)
    else:
        render_template('index.html')
```

* **The Request Object**

    1. Import request
    2. Use **request.method** to get current request method
    3. Use **request.form[]** to access request data in **POST** method
    4. Use **request.args.get()** to access parameters submitted in URL with **GET** method

```python
from flask import request
from flask import render_template


@app.route('/', methods=['POST', 'GET'])
def index():
    if request.method == 'POST':
        location = request.form['location'].strip()
        unit = request.form['unit']
        if request.form['submit'] == 'Search':
            result = ...
            return render_template('weather.html', weather=result)
        elif request.form['submit'] == 'History':
            result = ...
            return render_template('history.html', history=result)
    else:
        submit = request.args.get('submit', '')
        if submit == 'Help':
            result = ...
            return render_template('help.html', help=result)
        else:
            return render_template('index.html')
```

* **Run Flask app**

For Windows
```
setx FLASK_APP weather_report_web0.py
flask run
    * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

The server is only accessible from your own computer, if you have the debugger mode disabled or trust the users on your network, then you can make it publicly available like this:

```
flask run --host=0.0.0.0
    * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
```

* **Debug Mode**

```
setx FLASK_DEBUG 1
flask run
```
* **Run as Python script**

Or add **app.run()**, then just run the py script

```
app = Flask(__name__)

if __name__ == "__main__":
    app.run(debug=True)
    
```
```
> py weather-report-web0.py
Running on http://127.0.0.1:5000/ (Press CTRL+C to quit
Restarting with stat
Debugger is active!
Debugger pin code: 112-163-277
```
    









