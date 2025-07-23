# Setting up to use DDD with transport and client over WiFi

DDD uses phones that move between connected and disconnected areas as transports.
These transports are not trusted: they can be malicious and try and alter, read data they carry, and discard data.
We use Signal's double ratchet protocol to protect data as it travels between end clients and the DDD server on the internet.

Because transports are not trusted, anyone can be a transport!
This makes onboarding a new transport super easy: they just need to install our software, and they are done.

Note: there is one trust point we have with transports: when a disconnected phone needs to install our software, they need to get it from somewhere.
Transports can provide clients with the ability to install the DDD software in a disconnected area.
**If you install DDD software from a transport, MAKE SURE YOU TRUST THE TRANSPORT!**

Here is a short video to show how DDD software is initially set up and used in a disconnected area:

{% include youtube.html id="cMpdkKUFbkc" %}

## Installing a transport

Here are a couple of notes when installing a transport:

1. You only need to install the DDD Transport application from discdd.net.
2. You must enable the location permission in the WiFi tab for WiFi to work.
   (It seems strange to need a location permission, but the WiFi information
   is sometimes used to figure out location. We do not use it for location.)
3. The first time a new client connects to your phone, you must manually accept
   the connection.
   This is super annoying, but it is required by Android.
   We will be switching to a different version of WiFi in the future to fix this.
4. You will probably want to enable background uploading. 1 minute is probably too
   often, but setting background uploading will make transporting DDD data happen
   without having to do anything (except for accepting new clients as mentioned above :'( )
5. You need to sync with the server before any clients will exchange data with you.
   You might see mentions of a "recency blob".
   This is data that is cryptographically signed by the server and bound to a transport
   that lets clients know that they are talking to a transport that exchanges data
   with the server that they are interested in.

## Installing a client

Here are some notes on installing a client:

1. You will need the DDD client and DDD mail apps.
   Without the DDD mail app, the DDD client doesn't do much,
   and without the DDD client, the DDD mail app cannot send and receive data.
   You can install these apps from https://discdd.net or from a transport that
   shares the apps.
   **If you install from a transport, make sure it is trusted!**
2. Don't delete and reinstall the DDD client withing reinstalling the
   DDD mail app.
   We are working on a fix to deal with this scenario gracefully, but right now we do not.
3. If you install over local wifi from a transport, you will need to delete that wifi
   connection before trying to exchange data with the transport.
