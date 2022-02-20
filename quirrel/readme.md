# Quirrel

Quirrel instance running on fly.io

### Deploy

Make sure you've deployed Redis first!

```shell
flyctl launch --name quirrel --no-deploy --copy-config
openssl rand -hex 16 # copy its output
flyctl secrets set PASSPHRASES= # paste the 32-character long password copied previously
flyctl secrets set REDIS_URL=redis://:paste_redis_password_here@cdg.quirrel-redis.internal:6379?family=6
flyctl deploy
```

### Set up your app

Copy the output of this command below and set it to the app's `QUIRREL_TOKEN` secret

```shell
curl --user ignored:paste_quirrel_passphrases_here -X PUT https://quirrel.fly.dev/tokens/yourapp
```
