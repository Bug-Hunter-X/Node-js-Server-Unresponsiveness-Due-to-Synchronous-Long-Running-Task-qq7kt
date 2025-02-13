# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js servers: unresponsiveness caused by long-running synchronous operations within the request handler.  The `bug.js` file contains code that simulates a 5-second CPU-bound task, blocking the event loop and preventing the server from handling subsequent requests.  The solution in `bugSolution.js` addresses this by using asynchronous operations and demonstrates proper handling of long-running tasks.

## How to reproduce

1. Clone the repository.
2. Navigate to the project directory.
3. Run `node bug.js`.
4. Attempt to make multiple requests to the server (e.g., using `curl` or a browser). You will observe that the server becomes unresponsive during the 5-second delay.
5. Run `node bugSolution.js` and repeat step 4. The improved server will handle requests concurrently without blocking.