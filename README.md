# Line-Bot-Python:  Step by step
Creating LINE bot using Flask + NGROK + LINE Bot message API

# Architecture design and concepts
Using LINE BOT to push multiple types of messages (image, location, text) to user based on the inputs from user

1) Create new LINE PROVIDER  
https://developers.line.biz/console/register/provider/


2) Create new LINE new channel 
Type = Messaging API


3) Issue Channel access token (long-lived)
Save 2 variables to input into Python code, All requests must have LINE signature(included in app.py) 
and token (secret key and channel key)


4) Set variable for BOTH token when app.py called
 Running flask on windows:

set LINE_CHANNEL_SECRET=e9e7++++++
set LINE_CHANNEL_ACCESS_TOKEN=tLHJIK++++++++++

Now both variables are ready to be called by APP.py  
(make sure running these 2 set commands before run "python app.py" on same session)


5) Run "ngrok http 8000"
Redirect https://NGROKxxxxxx  to localhost:8000


6) Run "python app.py" 


7) Add webhook on line channel config   (DON'T FORGET ADDING    /callback) for LINE Webhook to verify connection

https://developers.line.biz/console/channel/1630146909/basic/
Webhook URL Requires SSL= https://NGROKxxxxxx/callback

![image](https://user-images.githubusercontent.com/16419246/49954183-7f25db80-fec5-11e8-9124-2d080ec36c73.png)


8) Add QR code on line friend and start chatting with bot on LINE CHAT ROOM
*Note using all lowercase with following text
- profile
- bye
- confirm
- buttons
- carousel
- image_carousel
