``swag.http.response.response.HTTPResponse``
```python
.extra_headers: Union[Dict[str, str], None]
.date: Union[str, None] = None
.content_length: Union[int, None]
.content_type: str
.content_data: Union[str, bytes]
.status: int
.message: str
.server: str
.package() -> bytes
```

``extra_headers`` - additional headers, except Date, Server, Content-Type, Content-Length, Connection.

``content_length`` - length of a data.

``date`` - value for Date http header. By default is current datetime.

``content_type`` - value for Content-Type header, like ``text/html`` or ``application/json``.

``content_data`` - data that swag send in the body of the server response.

``status`` - http response status, like 200 or 500. By default is 200

``message`` - http message for client, like "Not Found", "OK", "Continue".

``server`` - value for Server http header. By default is ``"SwagServer"``

``package()`` - method that return bytes to be send over the socket.


A class that should always be returned from the endpoint.
Any endpoint must return this class, or to be more precise, 
BaseResponse with a specific package method that returns bytes.
