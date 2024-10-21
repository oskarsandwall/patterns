[< Back to the list of patterns](patterns_list.md)

# Chain of Responsibility Pattern

## Usage
This pattern allows an object to send a command without knowing which object will handle the request. 
Instead, multiple objects get a chance to process the request, forming a chain.

## Description
This behavioral pattern decouples sender and receiver. The sender therefore doesn't need 
to know who will handle the request and enabling adding and/or changing handlers without modifying client code.

How it works:
1. **Handler Interface:** Defines an interface for handling requests. It usually includes a method to set the next handler in the chain.
2. **Concrete Handlers:** Implement the handler interface and handle requests they are responsible for. If they can’t handle a request, they pass it to the next handler in the chain.
3. **Client:** Initiates the request and sends it to the first handler in the chain.

Support system example:
* Level 1 Support: Handles basic queries.
* Level 2 Support: Handles more complex issues.
* Level 3 Support: Handles the most complex issues.

If Level 1 can’t resolve the issue, it passes the request to Level 2, and so on.

### Benefits
* **Decouples sender and receiver:** The sender doesn’t need to know which object will handle the request.
* **Flexibility:** You can add or change handlers without modifying the client code.
* **Responsibility Sharing:** Multiple objects can handle the request, promoting a more distributed approach.

### Drawbacks
* **Uncertain Handling:** There’s no guarantee that a request will be handled if no handler is capable.
* **Performance:** Can be less efficient if the chain is long and the request has to pass through many handlers.

[< Back to the list of patterns](patterns_list.md)
