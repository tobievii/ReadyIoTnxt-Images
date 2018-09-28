This is the image for the tutorial https://github.com/IoT-nxt/IotNxt-NodeJS-RestService-PiZeroTo3B- 

-PiImage made , can restore on 8gb + SD cards
- Download PiBakery to edit wifi settings and or setup new wifi, VERY VERY important here , 
do not override your img accidentaly using pibakery , be sure to wait for the "update" notification 
to update the current pibakery recipie , then just go to startup, next boot and then add wifi settings 
in networking , VNC already enabled 

-Download Angry IP scanner or the scanner of your choice to find the pi on your new network. if you cannot see the unit in your network and 
the unit seems stuck on boot with pibakery then simply restart the unit after 5minutes of waiting and theunit should connect to your network

Go into the desktop folder and the Nodejs , in src change the following values : replace ******

const https = require('https');

function postToIoTnxt() {
    var packet = { "id": "**uniqueDeviceid***", "data": { "**sensor value name**": 1, "y": 2 } }
    const postData = JSON.stringify(packet);
    const options = {
        hostname: '*****.iotnxt.io',
        port: 443,
        path: '/api/v3/data/post',
        method: 'POST',
        headers: {
            'Authorization': 'Basic ' + Buffer.from("api:key-*********").toString('base64'),
            'Content-Type': 'application/json',
  
  now save and restart and see if you get the values in your API screen