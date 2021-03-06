dante config can be built with
```
ruby dante_config_generator.rb [FILENAME]
```
result will be written into `FILENAME` (`danted.conf` by default) and can be found [in the repo](danted.conf).

`ruby` on the host is not needed for building docker image, config is generated inside docker.

Only Telegram IPs (i. e. IPs administered by MNT-TELEGRAM, pulled from [RIPE NCC database](https://www.ripe.net/))
and domains (telegram.dog, telegram.me, telegram.org, stel.com, t.me) are accessible, all other traffic is forbidden.

Docker image can be pulled from [Docker hub](https://hub.docker.com/r/ojab/dante-telegram/)
```
docker pull ojab/dante-telegram
```

Simple demo:
```sh
docker-compose build
docker-compose up
curl --socks5 localhost:1080 http://web.telegram.org/
```
feel free to start/use resulting docker image however you want

If you need any other feature (i. e. authentication by username/password), feel free to [create an issue](https://github.com/ojab/docker-dante-telegram/issues/new) or pull request.
