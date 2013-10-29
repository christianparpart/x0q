### x0q - X zero Queue daemon

#### HTTP client API

Links against x0 http server api to expose HTTP API.

    PUT /:queue                     Puts an item onto the queue
      [Priority: NUMBER]              with an optional priority.
      payload                         queue payload 

    GET /:queue                     Pops an item from the queue
      [Expect: item]                  optionally indicate, that this is blocking (instead non-blocking).

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

