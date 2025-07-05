
### Run
```shell
cloudflared tunnel --config /etc/cloudflared/config.yml run traefik-tunnel
```

### Setup route
```shell
cloudflared tunnel route dns <TUNNEL_NAME or TUNNEL_UUID> <hostname>
```

