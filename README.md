## Mosquito config ##

* sudo apt-add-repository ppa:mosquitto-dev/mosquitto-ppa
* sudo apt-get update
* sudo apt-get install mosquitto
* cd /etc/mosquitto
* cp /etc/mosquitto/mosquitto.conf.example ./mosquitto.conf
* /usr/share/doc/mosquitto/examples/mosquitto.conf.example
* vim mosquitto.conf
* allow_anonymous false
* password_file mosquitto.pwd
* save changes on mosquitto.conf
* create user:
* sudo mosquitto_passwd -c mosquitto.pwd username (pick one)
* You'll be prompted for the password
* change : password_file mosquitto.pwd
* sudo mosquitto -c /etc/mosquitto/mosquitto.conf
* sudo mosquitto -d
