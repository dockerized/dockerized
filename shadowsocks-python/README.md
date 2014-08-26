### Edit config.json

```json
{
    "server_port":10086,
    "password":"xxxxxxxxx",
    "method": "aes-256-cfb",
    "timeout":600
}
```

### Build && Run

```bash
docker build -t yourname/shadowsocks-python .
docker run -p 10086:10086 -d yourname/shadowsocks-python
```
