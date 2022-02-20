# Redis

Redis instance running on fly.io

### Deploy

This should be deployed before Quirrel as it depends on Redis to run.

```shell
flyctl launch --name quirrel-redis --no-deploy --copy-config
flyctl volumes create redis_data --region cdg
openssl rand -hex 16 # copy its output
flyctl secrets set REDIS_PASSWORD=paste_redis_password_here # paste the 32-character long password copied previously
flyctl deploy
```
