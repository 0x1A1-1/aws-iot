# AWS-IOT
===========
Record aws iot setup

* Raspberry Pi 
* AWS account

Raspberry Setup
------------------
[https://www.raspberrypi.org/downloads/]
Require a keyboard, mouse and HDMI

### Important Document
http://docs.aws.amazon.com/iot/latest/developerguide/iot-device-sdk-node.html

Setup NodeJs
```
curl -sL https://deb.nodesource.com/setup_4.x | sudo bash -
sudo apt-get install nodejs
sudo apt-get install npm
```

Setup ssh to Raspberry Pi:
--------------------------------
1. sudo raspi-config
   * find ssh setting and enable
   * also setup password for unix system
***(alternative: sudo service ssh status // to check if ssh is up and running
2. sudo apt-get install ssh
2. ifconfig
   * check ip address

Install SDK
----------------
```npm install https://github.com/aws/aws-iot-device-sdk-js```

Remote in AWS console
-------------------------
1. register for an account -> **Get Started**
2. **create** a thing under aws-iot
3. **Create device** -> select nodeJs and save all the generated files
4. save file at ```https://www.symantec.com/content/en/us/enterprise/verisign/roots/VeriSign-Class%203-Public-Primary-Certification-Authority-G5.pem``` within same directory

Testing
--------
Get the test node js file 
```
curl https://raw.githubusercontent.com/sreid/aws-iot-raspberry-pi-how-to/master/pi.js > pi.js
```
Pay attention to configure -> DO NOT MISS OUT REGION
```
var thingShadows = awsIot.thingShadow({
   keyPath: './certs/<your_cert>-private.pem.key',
  certPath: './certs/<your_cert>-certificate.pem.crt',
    caPath: './certs/rootCA.pem',
  clientId: myThingName,
    region: 'us-east-1'
});
```
