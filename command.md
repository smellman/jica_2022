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
cd
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
dpkg -i /home/btm/Downloads/code_1.63.2-1639562499_amd64.deb
```
## install qgis
```
apt install gnupg software-properties-common
wget -qO - https://qgis.org/downloads/qgis-2021.gpg.key | gpg --no-default-keyring --keyring gnupg-ring:/etc/apt/trusted.gpg.d/qgis-archive.gpg --import
chmod a+r /etc/apt/trusted.gpg.d/qgis-archive.gpg
add-apt-repository "deb https://qgis.org/ubuntu $(lsb_release -c -s) main"
apt update
apt install qgis qgis-plugin-grass
git clone https://github.com/mapbox/mbutil.git
cd mbutil
python3 setup.py install
```
# Setup docker
```shell
su –
nano /etc/resolv.conf
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
