#!/bin/bash

# API_KEY 
apikey=ea664cded5ef5841bc3e94717607c9e3

response=$(curl -s http://muslimsalat.com/daily.json?key=$apikey&jsoncallback=?)
if [ $(dpkg-query -W -f='${Status}' jq 2>/dev/null | grep -c "ok installed") = 0 ]
then
 	sudo apt-get install jq -y
fi
fajr=$(echo $response | jq -r '.items[0].fajr')
ishraq=$(echo $response | jq -r '.items[0].shurooq')
dhuhr=$(echo $response | jq -r '.items[0].dhuhr')
asr=$(echo $response | jq -r '.items[0].asr')
maghrib=$(echo $response | jq -r '.items[0].maghrib')
isha=$(echo $response | jq -r '.items[0].isha')

notify-send "Namaz Timings" "\n fajr $fajr \n ishraq $ishraq \n dhuhr $dhuhr \n asr $asr \n maghrib $maghrib \n isha $isha"



