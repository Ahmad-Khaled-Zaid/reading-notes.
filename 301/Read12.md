## Which HTTP Status Code to Use for Every CRUD App
The HTTP specification defines many status codes we can use when responding to our clients. Some APIs only use the most basic codes and define their own error signaling mechanisms on top of it; others want to make full use of HTTPs collection of codes to tell their clients what’s going on. If you belong to the latter, this article is for you. This guide walks through the various CRUD operations and which status codes you should be using for clean API design.

Status ClassesPermalink
If we understand the class a status code is in, we can locate problems more quickly.

- 100 - 199Permalink
These are informational status codes; they usually tell the client that the header part of the request has been received and the server will try to comply with a transmission demand of the client. Like using a different protocol or telling the client that its request will fail before they start sending the body.

- 200 - 299Permalink
These are the success codes. They tell the client that its request was accepted. In case of asynchronous processing of a request (202), this doesn’t mean the request was successfully processed only that it met all validation requirements at the time of sending.

- 300 - 399Permalink
These are redirection codes. They tell the client that the resource they are requesting isn’t available at the expected location anymore. This can have multiple reasons, be temporary or permanent, but the client has to issue a request to the new location.

- 400 - 499Permalink
These are the client error codes. They are all about invalid requests a client sent to a server. There are several causes to this, timeouts, wrong URI, missing authentication, etc. A client is sending incorrect input and should confirm the input parameters are correct before retrying the request.

- 500 - 599Permalink
These are the server error codes. Often they indicate problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server. These errors can be temporary or permanent. Usually it’s best for the client to retry the same request.

Custom ClassesPermalink
Custom classes, that is, classes above 599 aren’t permitted but used by some services anyway. For API designers, they are relevant as bad examples. API client creators, however, have to deal with them.

So while they aren’t usually allowed, be prepared to meet them in the wild.

