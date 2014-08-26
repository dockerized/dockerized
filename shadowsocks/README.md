### Edit config.json

```json
{
    "server_port":10010,
    "password":"xxxxxxxxx",
    "method": "aes-256-cfb",
    "timeout":600
}
```

### Build && Run

```bash
docker build -t xiocode/shadowsocks .
docker run -p 10010:10010 -d yourname/shadowsocks
```
