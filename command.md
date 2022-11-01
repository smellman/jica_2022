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
```shell
apt install build-essential libsqlite3-dev zlib1g-dev
git clone https://github.com/felt/tippecanoe.git
cd tippecanoe
make
make install
cd
```
## install nodejs and charties
```shell
apt install curl
curl -fsSL https://deb.nodesource.com/setup_18.x | bash -
apt install nodejs
git clone https://github.com/unvt/charites.git
cd charites
npm install
npm run build
npm install --global .
cd
```
## install visual studio code
```shell
dpkg -i /home/btm/Downloads/code_1.63.2-1639562499_amd64.deb
```
## install qgis
```shell
apt install gnupg software-properties-common
mkdir -m755 -p /etc/apt/keyrings
wget -O /etc/apt/keyrings/qgis-archive-keyring.gpg https://download.qgis.org/downloads/qgis-archive-keyring.gpg
nano /etc/apt/sources.list.d/qgis.sources
```

add below:

```
Types: deb deb-src
URIs: https://qgis.org/debian
Suites: bullseye
Architectures: amd64
Components: main
Signed-By: /etc/apt/keyrings/qgis-archive-keyring.gpg
```

Then, install qgis:

```
apt update
apt install qgis qgis-plugin-grass
```
## install mbutils
```shell
git clone https://github.com/mapbox/mbutil.git
cd mbutil
python3 setup.py install
cd
```
# Setup docker
```shell
su –
usermod –aG docker (your login name)
reboot
docker run helloworld
```
# tippecanoe
```shell
tippecanoe -o lka.mbtiles -L airp:airp_lka.geojson -L builtupp:builtupp_lka.geojson -L coastl:coastl_lka.geojson -L inwatera:inwatera_lka.geojson -L polbnda:polbnda_lka.geojson -L polbndl:polbndl_lka.geojson -L raill:raill_lka.geojson -L riverl:riverl_lka.geojson -L roadl:roadl_lka.geojson
```
# start Tileserver GL
```shell
docker run --rm -it -v $(pwd):/data -p 8090:80 maptiler/tileserver-gl -p 80
```
# charites
```shell
mkdir work
cd work
cp ~/Downloads/global_map_style.json style.json
charites convert style.json
charites serve style.yml
```
