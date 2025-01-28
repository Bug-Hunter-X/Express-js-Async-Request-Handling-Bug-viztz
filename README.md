# Express.js Async Request Handling Bug

This repository demonstrates a common issue in Express.js applications where asynchronous operations within request handlers are not properly awaited, resulting in premature responses from the server before the asynchronous operation completes.

## Bug Description

The `bug.js` file contains an Express.js server that handles POST requests to the `/data` endpoint.  The server attempts to process incoming data asynchronously using `setTimeout`. However, the server sends a response (`res.send('Data received')`) before the `setTimeout` callback (which simulates an asynchronous operation) finishes. This can lead to inconsistent behavior and data loss.

## Solution

The `bugSolution.js` file provides a corrected version of the server, where the response is sent only after the asynchronous operation is complete. This ensures that data processing is finished before acknowledging the request to the client.