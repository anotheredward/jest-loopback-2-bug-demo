This repo demonstrates an issue I am having with running jest 2 tests that load server.js
We need to load server.js to acess the models property to test various creation functions for models without going through the api endpoints

Repro
1. `npm install` 
2. `npm test` 
See that it is unable to load some middleware and crashes

Error#:##

```
 FAIL  ./example.test.js
  ● Test suite failed to run

    Cannot resolve path "loopback/server/middleware/urlNotFound"

      at resolveAppPath (node_modules/loopback-boot/lib/compiler.js:363:15)
      at resolveAppScriptPath (node_modules/loopback-boot/lib/compiler.js:686:22)
      at resolveMiddlewarePath (node_modules/loopback-boot/lib/compiler.js:593:29)
      at node_modules/loopback-boot/lib/compiler.js:481:24
      at Array.forEach (native)
      at node_modules/loopback-boot/lib/compiler.js:480:18
      at Array.forEach (native)
      at node_modules/loopback-boot/lib/compiler.js:475:30
      at Array.forEach (native)
      at buildMiddlewareInstructions (node_modules/loopback-boot/lib/compiler.js:473:15)
      at compile (node_modules/loopback-boot/lib/compiler.js:62:5)
      at bootLoopBackApp (node_modules/loopback-boot/index.js:153:22)
      at Object.<anonymous> (server/server.js:23:1)
      at Object.<anonymous> (example.test.js:1:94)
      at process._tickCallback (node.js:369:9)
      ```
