``swag.http.response.response.HTTPResponse``
A class that should always be returned from the endpoint.
Any endpoint must return this class, or to be more precise, BaseResponse with a specific package method that returns bytes.
