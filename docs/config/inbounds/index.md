## Simplified usage

- HTTP Proxy

```yaml
# port of HTTP proxy server
port: 7890
```

- SOCKS Proxy

```yaml
socks-port: 7891
```

!!! Tip
    Top-level HTTP/SOCKS/Mixed/Tproxy will be converted into inbounds add included in `listeners`

    | Type       | Mapped inbound name  |
    | ---------- | -------------------- |
    | `HTTP`     | `HTTP-IN`            |
    | `SOCKS`    | `SOCKS-IN`           |
    | `Mixed`    | `MIXED-IN`           |
    | `Tproxy`   | `TPROXY-IN`          |

## Supported Inbound Types

- http
- socks
- mixed
- tproxy
- tunnel


## Common Options

``` yaml
listeners:
  - name: in-http
    type: http #(3)
    port: 15201
    listen: 127.0.0.1 #(4)
    proxy: out-tuic #(1)
    ...... #(2)
```

1.  Optional, outbound name. Any traffic through this inbound will directly go to `proxy`
2.  There could be more fields in real inbound
3.  [Allowed Values](./#supported-inbound-types)
4.  [Type: BindAddress](../../config/types/#bindaddress) <br> Address of inbound server
