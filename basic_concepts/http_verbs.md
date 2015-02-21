# HTTP Verbs

The Verbs, or more commonly known as Methods, are indicators of actions in the uniform interface that the HTTP protocol is.

Every request using the HTTP protocol must inform one the HTTP Methods so that the server knows how to respond properly to the request.

Here we will list the four most used Methods involved in the management of an API. This are the GET, POST, PUT and DELETE Methods.

This section draws heavily from the [HTTP/1.1](http://www.w3.org/Protocols/rfc2616/rfc2616.html) memo, you should check it out if you'd like to know more.

###GET

The GET Methods should be use when your intention is to obtain a collection or an entity from a server. GET is said to be one of the *safe* methods, it is regarded as an action without side effects.
This means that the action should be only meant for retrieval of a resource, and never another action like updating or deleting a resource or part of it.

You can obviously make it so, but the user cannot be held responsible for any side effect, since he didn't request for them.
