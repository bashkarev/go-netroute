Go Netroute
===

A cross-platform implementation of the `gopacket/routing.Router` interface.

This library uses `gopacket` for linux, `x/net/route`
for mac, and `iphlpapi.dll` for windows.

Usage
---

```
import (
    netroute "github.com/willscott/go-netroute"
)

func main() {
    r, err := netroute.New()
    if err != nil {
        panic(err)
    }
    iface, gw, src, err := r.Route(net.IPv4(127, 0, 0, 1))
    fmt.Printf("%v, %v, %v, %v\n", iface, gw, src, err)
}
```
