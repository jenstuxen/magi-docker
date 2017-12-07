# magi-docker
Dockerized xmg miner for targets amd64, rpi, orangepizero

It builds from git repository https://github.com/magi-project/m-cpuminer-v2.

Raspberry pi images based on resin images https://resin.io/.

Idea from https://www.novaspirit.com/2017/10/19/crypto-mining-sbc/

# Examples
## Latest amd64 alpine
```bash
#OBS this will go to my account
docker run --rm -it jenstuxen/magi-docker:latest m-minerd -o stratum+tcp://xmg.suprnova.cc:7128 -u leaRINSIScH.magi -p password
```
## Latest rpi2 (interactive)
```bash
docker run --rm -it jenstuxen/magi-docker:rpi2 m-minerd -o stratum+tcp://xmg.suprnova.cc:7128 -u USERNAME.WORKERNAME -p password
```
## Latest orangepizero (background)
```bash
docker run --rm -d jenstuxen/magi-docker:orangepizero m-minerd -o stratum+tcp://xmg.suprnova.cc:7128 -u USERNAME.WORKERNAME -p password
```
