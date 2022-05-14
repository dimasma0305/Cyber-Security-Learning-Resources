# HTTP request methods

HTTP defines a set of **request methods** to indicate the desired action to be performed for a given resource. Although they can also be nouns, these request methods are sometimes referred to as _HTTP verbs_. Each of them implements a different semantic, but some common features are shared by a group of them: e.g. a request method can be safe, idempotent, or cacheable.

## GET

The `GET` method requests a representation of the specified resource. Requests using `GET` should only retrieve data.

## HEAD

The `HEAD` method asks for a response identical to a `GET` request, but without the response body.

## POST

The `POST` method submits an entity to the specified resource, often causing a change in state or side effects on the server.

## PUT

The `PUT` method replaces all current representations of the target resource with the request payload.

## DELETE

The `DELETE` method deletes the specified resource.

## CONNECT

The `CONNECT` method establishes a tunnel to the server identified by the target resource.

## OPTIONS

The `OPTIONS` method describes the communication options for the target resource.

## TRACE

The `TRACE` method performs a message loop-back test along the path to the target resource.

## PATCH

The `PATCH` method applies partial modifications to a resource.

## Specifications
<table><thead><tr><th>Specification</th><th>Title</th><th>Comment</th>
 </tr></thead><tbody><tr><td><a href="https://datatracker.ietf.org/doc/html/rfc7231#section-4" class="external" rel=" noopener">RFC 7231, section 4: Request methods</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td><td>Specifies GET, HEAD, POST, PUT, DELETE, CONNECT, OPTIONS, TRACE.</td></tr><tr><td><a href="https://datatracker.ietf.org/doc/html/rfc5789#section-2" class="external" rel=" noopener">RFC 5789, section 2: Patch method</a></td><td>PATCH Method for HTTP</td><td>Specifies PATCH.</td></tr></tbody></table>