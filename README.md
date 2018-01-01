# magi-docker
Dockerized xmg miner for targets amd64, rpi, orangepizero

It builds from git repository https://github.com/magi-project/m-cpuminer-v2.

Raspberry pi images based on resin images https://resin.io/.

Idea from https://www.novaspirit.com/2017/10/19/crypto-mining-sbc/.

# Examples
OBS set to mine on my account, replace `-u leaRINSIScH.magi -p password` with your own
## Latest by auto detected architecture
* benchmark
```bash
docker run --rm -it jenstuxen/magi-docker m-minerd --benchmark
```
* example
```bash
docker run -d jenstuxen/magi-docker m-minerd -o stratum+tcp://96.43.139.10:3333 -u fxyn4w6u34gy535gh.user -p password
```
## specify arhitecture/device/os (see tags)
```bash
docker run -d jenstuxen/magi-docker:alpine-armhf-rpi2 m-minerd -o stratum+tcp://96.43.139.10:3333 -u fxyn4w6u34gy535gh.user -p password
```

# Tags
https://hub.docker.com/r/jenstuxen/magi-docker/tags/

# Build
```bash
cd magi-docker
cd rpi/2/ #or your specific device
docker build -t local/magi-docker:rpi2 .
docker run -it local/magi-docker:rpi2 m-minerd --benchmark
```
