## Version 0.1-alpha

DDD Client and Transport use an implementation of Double Ratchet to end-to-end encrypt messages between the Clients and the Server.
This means Transports will not be able to see the data sent between client and server.

We use WiFi Direct to transfer data and Android does expose WiFi Direct name of the phone.
However, we do not collect this information.
The names displayed when exchanging data, and logged in the debug logs of the phone.
Usually, the logs will be deleted, but in the event of a crash the logs will be uploaded to the server for analysis.

The clients tell the server the transport IDs that they have seen so that the server can know which transports can be used to send data to which client,
but this transport ID is a randomly generated number and is not connected to any personal identifiable information.

When used with the email application, emails in transit are encrypted from the client to the server, but are stored in the clear on the server.
They are deleted once the emails have been transmitted.
The server only inspects the senders and receivers of the emails to route them.
We only share emails with the recipient servers.
We will comply with government orders when required.
We encourage our users to additionally employ the end-to-end encryption features of the email clients they use.
