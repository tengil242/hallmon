# Build image
```bash
docker build -t tengil242/hallmon .
```
# View images
```bash
docker images
```
# Start
```bash
docker run -d -p 192.168.242.242:2222:22 -e ROOT_PASS="front242" tengil242/hallmon
```
# View started
```bash
docker ps -a
```
# View logs for started container
```bash
docker logs <id>
```
---

# On hugin.local (raspbian / raspberry2)

sudo apt-get install avahi-daemon libnss-mdns x11vnc

Make sure that the /etc/nsswitch.conf contains this line:
  hosts: files mdns4_minimal [NOTFOUND=return] dns mdns4
Make sure that file  /etc/avahi/services/ssh.service containing the following lines:

```xml
<?xml version="1.0" standalone='no'?><!--*-nxml-*-->
<!DOCTYPE service-group SYSTEM "avahi-service.dtd">
<service-group>
 <name replace-wildcards="yes">%h</name>
 <service>
  <type>_ssh._tcp</type>
  <port>22</port>
 </service>
</service-group>
```

http://stackoverflow.com/questions/32361132/screen-sharing-between-raspberry-pi-and-mac-osx

# For chromium https://launchpad.net/~canonical-chromium-builds/+archive/ubuntu/stage

# SHOWSTOPPER! https://bugs.chromium.org/p/chromium/issues/detail?id=525751
# chromium will not work with latest version. x86 / 64 bit thingy!?
# nighty-night  //O

```bash
# THIS IS THE ONLY WAY TO GET CHROMIUM ON JESSIE!
# THIS WILL ONLY WORK ON A Pi2!
# You may be able to use the older one in the Wheezy repo, but that's v22


sudo chmod 777 /etc/apt/sources.list.d/.
sudo echo "deb http://ppa.launchpad.net/canonical-chromium-builds/stage/ubuntu wheezy main" > /etc/apt/sources.list.d/chromium-ppa.list
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys DB69B232436DAC4B50BDC59E4E1B983C5B393194
```

# Install all deps
```bash
sudo apt-get update
sudo apt-get install libmysqlclient-dev ruby-dev ruby2.3-dev ruby-bundler nodejs build-essential gcc libxml2 libxml2-dev libxslt1-dev htop chromium-browser
sudo gem install dashing

```
