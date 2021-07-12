# HTTP Server

We need you to write an HTTP Server from scratch!

The HTTP server should be done in C#. Both languages have good socket and thread libraries upon which to build, and the code is portable. Your HTTP Server should be packaged and runnable on any computer. You may use the classes/methods contained in the raw TCP socket and thread libraries of language, but nothing else. If done in C#, System.Net.Http library should not be used.

Begin by focusing on meeting the basic HTTP Server requirements and, once completed, move on to the Advanced HTTP Server requirements.

## Basic HTTP Server

The server should serve a hello world message in response to a request of the root. There must exist the facility to point the server to a directory, from which to serve files. It should respond with the appropriate error code if a requested file does not exist. The server must be able to handle multiple simultaneous requests.

The solution should have appropriate acceptance testing. The server should pass all tests in [CobSpec](https://github.com/8thlight/cob_spec). Additionally, you should add a test of your own to cover a part of the HTTP spec not currently covered.

We want you to search out the [HTTP spec](https://tools.ietf.org/html/rfc7230) to uncover the details of these requirements.

## Advanced HTTP Server

Once you have completed the basic HTTP server, we want you to push your design skills. Modify the server to be able to generate content dynamically. This will also require you to dig into post parameters or parsing query strings and deal with persistent state. 

We would like the server to be able to serve a previous tic tac toe game or equivalent project done during acceleration.

Good luck!

## Important

Please submit your code in a private fork of this repository. Please don't share this problem or your solution with anyone else. We would like to keep this solution as a measure for a protege's progress, for this to be effective please keep this off public forums and avoid pairing with others when doing this solution.
