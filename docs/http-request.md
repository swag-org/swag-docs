# HTTPRequest
HTTPRequest is a first argument that you endpoints must have.
HTTPRequest is a converted data that swag collect from socket response.


```python
HTTPRequest.from_string(raw_string: str, ip: int) -> HTTPRequest
```
Returns the `HTTPRequest` itself. You probably won't need to use this static method directly.


```python
HTTPRequest.method: HTTPMethod
HTTPRequest.headers: Dict[str, str]
HTTPRequest.route: str
HTTPRequest.ip: Tuple[str, int]
```

**.method** - request method. You don't manage the requests by endpoints in Swag, maybe i'll remove this field, because you really know which method handles that endpoint.


**.headers** - parsed HTTP headers


**.route** - string path, like ``/hello/swag``


**.ip** - actually its a ip and port where did the request come from

