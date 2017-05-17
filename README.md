Prerequisites
Before starting this tutorial, you will need:

An Ubuntu 16.04 server with a non-root, sudo-enabled user and basic firewall set up

1. Log in to your server as the root user.
2. Use the adduser command to add a new user to your system.  
`adduser username`  

Follow the prompts to set the new user's information. It is fine to accept the defaults to leave all of this information blank.Changing the user information for username  

```
   Enter the new value, or press ENTER for the default
    Full Name []:
    Room Number []:
    Work Phone []:
    Home Phone []:
    Other []:
Is the information correct? [Y/n]
```

3. Use the usermod command to add the user to the sudo group.

`usermod -aG sudo username`

4. Login using the new account and issue the following command:  

`sudo apt-get install mosquitto mosquitto-clients`

5. Enable Firewall  
`sudo ufw allow 1883`

6. Issue new password:  
`sudo mosquitto_passwd -c /etc/mosquitto/passwd sammy`

7. open new configuration for mosquitto  
`sudo nano /etc/mosquitto/conf.d/default.conf`

8. Paste the following:  
```
allow_anonymous false
password_file /etc/mosquitto/passwd
```
9. Restart mosquitto  
`sudo systemctl restart mosquitto`
10. Subscribe and publish.  
```
mosquitto_sub -h localhost -t test -u "sammy" -P "password"
mosquitto_pub -h localhost -t "test" -m "hello world" -u "sammy" -P "password"
```
11. Configuring over websockets.  

`sudo nano /etc/mosquitto/conf.d/default.conf`

Add the following lines and restart mosquitto:

```
listener 1883
listener 8080
protocol websockets
```
