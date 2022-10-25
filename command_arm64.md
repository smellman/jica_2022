# install software
## install basic software
```shell
su –
apt update
apt install git
apt install docker.io
apt install p7zip-full
```
## install tippecanoe fork
```
apt install build-essential libsqlite3-dev zlib1g-dev
git clone https://github.com/felt/tippecanoe.git
cd tippecanoe
make -j
make install
```
## install nodejs and charties
```
apt install curl
curl -fsSL https://deb.nodesource.com/setup_18.x | bash -
apt install nodejs
git clone https://github.com/unvt/charites.git
cd charites
npm install
npm run build
npm install --global .
```
## install visual studio code
```
dpkg -i /home/btm/Downloads/code_1.17.2-1665612990_arm64.deb
```
