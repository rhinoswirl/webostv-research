# Luna Service Monitor

It is possible to debug, monitor and inspect Luna Service Bus services using `ls-monitor`.

Running the service without parameters will log the traffic going through the services.

```
Usage:
  ls-monitor [OPTION...] - Luna Service monitor

Help Options:
  -h, --help                           Show help options

Application Options:
  -f, --filter=com.palm.foo            Filter by service name (or unique name)
  -l, --list                           List all entities connected to the hub
  -s, --subscriptions                  List all subscriptions in the system
  -i, --introspection=com.palm.foo     List service methods and signals
  -v, --api-version=com.palm.foo       Get service API version
  -m, --malloc                         List malloc data from all services in the system
  -d, --debug                          Print extra output for debugging monitor but with UNBOUNDED MEMORY GROWTH
  -c, --compact                        Print compact output to fit terminal. Take precedence over debug
  -j, --json                           Print JSON formatted output for easier parsing. Take precedence over debug
  -t, --sort-by-timestamps             Sort output by timestamps instead of serials
  --dump-hub-data-csv                  Dump hub data in CSV format

Compact mode symbols:
   >*      signal
   >|      cancel method call
    >      method call
   <       reply
```


Example commands:

```sh
# Log traffic
ls-monitor

# List connected clients
ls-monitor -l

# Inspect supported requests
ls-monitor -i com.webos.service...
```