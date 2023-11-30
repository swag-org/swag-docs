# Get started
## Here the simple `Hello, world!` app written in swag:
```python
from swag.app.app import SwagApp
from swag.app.config import SwagAppConfig
from swag.http.response import HTTPResponse
from swag.http.request import HTTPRequest


my_config = SwagAppConfig(port=6969, host="0.0.0.0")
app = SwagApp(config=my_config)

@app.route("GET", "/hello/{world}")
def hello(request: HTTPRequest, world: str):
    return HTTPResponse(
        f"""
<h1>Hello {world}!</h1>
""".strip(),
        content_type="text/html")
```

Firstly, we just specify the `configuration` of our application, it's really simple.

And after run that, we can see on http://0.0.0.0:6969/hello/swag
```html
<h1>Hello, swag!</h1>
```
### The first thing that you need to know:
**IF YOU WANT TO CREATE A PLACEHOLDER IN THE PATH (like `world: str` in this example), YOU NEED TO EXPLICITLY SPECIFY ITS TYPE.**


Available types:


- str
* int
* float


### And the second thing:
It is not necessary to specify the type of the first argument passed, you can usually call it `request` and it is passed automatically. Always.

### Run it
You dont need other packages like unicorn, gunicorn, or even nginx.


Just run in your shell:
`python main.py`

