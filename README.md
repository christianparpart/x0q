### x0q - X zero Queue daemon

#### HTTP client API

Links against x0 http server api to expose HTTP API.

    PUT /:queue                     Puts an item onto the queue
      [Priority: NUMBER]              with an optional priority.
      [Expect: pop]                   synchronously block until the item got popped.
      payload                         queue payload 

    GET /:queue                     Pops an item from the queue
      [Expect: item]                  optionally indicate, that this is blocking (instead non-blocking).

    GET /:queue/stats               Gets queue statistics for given queue.

    POST /:queue/clear              Clears all items in the queue

#### Worker API

CBOR / JSON


#### x0q CLI

    x0q [options]

    -c,--config=FILE        path to configuration file.
    -d,--daemonize          Daemonizing, fork into background.
    -b,--http-bind=IPADDR   HTTP listener address.
    -p,--http-port=PORT     HTTP listener port.
    -B,--worker-bind        worker listener address.
    -P,--worker-port        worker listener port.


#### Implementation Goals

- Support multi threaded mode, e.g. either having a queue worker thread or non-blocking queues and a set of generic worker threads
- Resource constraints (queue item size, memory size, ...)

