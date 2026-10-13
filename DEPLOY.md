# Deploy — SANDBOX (IP only, no domain)

Container `maifocus-website` on SANDBOX host, port 8090 -> 80.

```bash
git clone -b develop https://github.com/menibl/maifocus-website.git && cd maifocus-website
sudo docker build -t maifocus-website:<sha> .
sudo docker run -d --name maifocus-website --restart unless-stopped \
  -p 8090:80 --log-opt max-size=10m --log-opt max-file=3 maifocus-website:<sha>
```
Rollback: keep previous container renamed `maifocus-website-before-<tag>`.
