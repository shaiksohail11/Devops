Installing JBoss Wild-Fly on Ubuntu
------------------------------------

Prerequisites
-------------
* In order to be able to install packages on your Ubuntu system, you must be logged in as a user with sudo privileges .

* The Manual steps for installing jboss-wildfly
  

```
Install Java OpenJDK 
sudo groupadd -r wildfly
sudo useradd -r -g wildfly -d /opt/wildfly -s /sbin/nologin wildfly
WILDFLY_VERSION=16.0.0.Final
wget https://download.jboss.org/wildfly/$WILDFLY_VERSION/wildfly-$WILDFLY_VERSION.tar.gz -P /tmp
sudo tar xf /tmp/wildfly-$WILDFLY_VERSION.tar.gz -C /opt/
sudo ln -s /opt/wildfly-$WILDFLY_VERSION /opt/wildfly
sudo chown -RH wildfly: /opt/wildfly
sudo mkdir -p /etc/wildfly
sudo cp /opt/wildfly/docs/contrib/scripts/systemd/wildfly.conf /etc/wildfly/
sudo cp /opt/wildfly/docs/contrib/scripts/systemd/launch.sh /opt/wildfly/bin/
sudo sh -c 'chmod +x /opt/wildfly/bin/*.sh'
sudo cp /opt/wildfly/docs/contrib/scripts/systemd/wildfly.service /etc/systemd/system/
sudo systemctl daemon-reload
sudo systemctl start wildfly
sudo systemctl status wildfly
sudo systemctl enable wildfly
```
* To access WildFly interface from the outside of your local network you need to open port `8080`

[Refer_Here](https://linuxize.com/post/how-to-install-wildfly-on-ubuntu-18-04/) For the official docs.