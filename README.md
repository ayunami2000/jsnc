jsnc - A JavaScript VNC (RFB) Server implementation
===================================================

This is a naive server implementation of the Remote Framebuffer Protocol. This
is a quick'n'dirty hack, not recommended for any form of productive use.

There are a few known issues:

  - It only does RAW encoding (requires lots of bandwidth!)
  - It has bugs in negotiation of encoding (thus only 24 true color
    works)
  - No security (password or other) support
  - Updating the screen isn't really supported

This library contains a small sample server which can be run using `npm start`

## Using the test server

First, in an empty directory, install this library and start the server:

    $ npm install git://github.com/johannes/jsnc.git
    $ npm start

Then connect using a VNC client. You should see the `test.png` image
displayed. On the console you can see output for different events.

## Library-usage

Add the library to your project:

    $ npm install --save git://github.com/johannes/jsnc.git

Now look at `node_modules/jsnc/server.js` for a sample client.

## Tested clients

The following clients where tested:

  - Remmina 0.9.99.1 - This works in 24 bit mode, but sometimes terminates
    after rendering our initial display content
  - Gtk VNC Viewer 0.4 - his works with default settings
  - jvncviewer - Tries to negotiate lower quality and fails

## License

This is trivial code after reading the RFB specification, thus no copyright is
claimed. If this perspective isn't shared MIT license can be used as fallback.
A file called `MIT.txt` is part of this distribution which contains those terms.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND