``swag.abstractions.methods``
HTTPMethod is a union of all available http methods. It's just a str, with one
of the possible values: "GET", "POST", "PUT", "DELETE", "PATCH", "OPTIONS",
"HEAD".

I think the best explanation is the source code:

```python

HTTPGetMethod = Type["GET"]
HTTPPostMethod = Type["POST"]
HTTPPutMethod = Type["PUT"]
HTTPDeleteMethod = Type["DELETE"]
HTTPPatchMethod = Type["PATCH"]
HTTPOptionsMethod = Type["OPTIONS"]
HTTPHeadMethod = Type["HEAD"]


HTTPMethod = Union[
    HTTPPostMethod,  HTTPGetMethod,
    HTTPPutMethod, HTTPDeleteMethod,
    HTTPPatchMethod, HTTPOptionsMethod,
    HTTPHeadMethod]
```


Note that you can use two different ways to define a method in app.route, with string like "GET", and with HTTPGetMethod:
```python
@app.route("GET", "/hello/{world}")
```

```python
@app.route(HTTPGetMethod, "/hello/{world}")
```

In any case, you can use what is more convenient for you. This will not affect the server response speed.
