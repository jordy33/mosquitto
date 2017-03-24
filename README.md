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
* mosquitto_sub -d -t hello/world -u dwim -P gpscontrol1
* ufw allow 1883
listener 1883  
protocol mqtt  
listener 9001  
protocol websockets  
* sudo service mosquitto restart

 wget http://mosquitto.org/files/source/mosquitto-1.4.11.tar.gz  
 tar -zxvf mosquitto-1.4.11.tar.gz  
 cd mosquitto-1.4.11  
   // in file config.mk set:   WITH_WEBSOCKETS:=yes  
 make  
 make install  
 mosquitto -v -c /etc/mosquitto/mosquitto.conf  
 
 
