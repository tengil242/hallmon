# Build image
docker build -t tengil242/hallmon .
# View images
docker images
# Start
docker run -d -p 192.168.242.242:2222:22 -e ROOT_PASS="apa242" tengil242/hallmon
# View started
docker ps -a
# View logs for started container
docker logs <id>

---

# On hugin.local (raspbian / raspberry2)

sudo apt-get install avahi-daemon libnss-mdns x11vnc

Make sure that the /etc/nsswitch.conf contains this line:
  hosts: files mdns4_minimal [NOTFOUND=return] dns mdns4
Make sure that file  /etc/avahi/services/ssh.service containing the following lines:

<?xml version="1.0" standalone='no'?><!--*-nxml-*-->
<!DOCTYPE service-group SYSTEM "avahi-service.dtd">
<service-group>
 <name replace-wildcards="yes">%h</name>
 <service>
  <type>_ssh._tcp</type>
  <port>22</port>
 </service>
</service-group>

http://stackoverflow.com/questions/32361132/screen-sharing-between-raspberry-pi-and-mac-osx

## sudo apt-get install libmysqlclient-dev ruby-dev ruby2.3-dev build-essential gcc libxml2 libxml2-dev libxslt1-dev

## sudo gem install dashing
