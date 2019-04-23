# CloudApp Wrapper Component

_NOTE: This repo was deprecated when we removed bots running from the browser._

The objective of this component is to allow the CloudApp to un at the browser reusing as much of the original CloudApp source code as possible. CloudApp is the Node.js App that executes bots at the cloud. Execution at the CloudApp starts at Run.js, a module designed to do the initial setup before passing the execution onto Root.js. All cloud specific initialization is at that Run.js module.

What we do here is that we replace that Run.js module with a module called BrowserRun.js which does a very similar initialization but in this case adapted to browser execution. It too then continues its execution at the Root.js module and from there nothing is touched at the original code.

However, there are some Node.js specific functionality that wont work at the browser, like Require for instance. For those very special cases, the CloudApp source code is transpiled in order to use browser based equivalents to keep things working in a similar way.
