## Mosquito config ##

* sudo apt-add-repository ppa:mosquitto-dev/mosquitto-ppa
* sudo apt-get update
* sudo apt-get install mosquitto
* cd /etc/mosquitto
* cp /etc/mosquitto/mosquitto.conf.example ./mosquitto.conf
* /usr/share/doc/mosquitto/examples/mosquitto.conf.example
* vim mosquitto.conf
* allow_anonymous false
* password_file /etc/mosquitto/mosquitto.pwd
* save changes on mosquitto.conf
* create user:
* To create dwim user:
* sudo mosquitto_passwd -c mosquitto.pwd dwim 
* You'll be prompted for the password
* sudo mosquitto -c /etc/mosquitto/mosquitto.conf
* sudo mosquitto -d
* apt install mosquitto-clients
* mosquitto_sub -d -t hello/world -u dwim -p gpscontrol1mosquitto_sub -d -t hello/world -u dwim -p gpscontrol1
* ufw allow 1883
