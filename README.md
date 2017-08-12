 
    # -*- coding: utf-8 -*- Humidity-Temp
import os
import time
import sys
from pubnub import Pubnub
import Adafruit_DHT as dht

pubnub = Pubnub(pub-c-b3be2fd6-c0f8-4c79-b497-aa905ce31c5e,sub-c-0b58259a-7ee8-11e7-a47c-def805f681ee)
channel = 'pi-house'

def callback(message):
    print(message)

#published in this fashion to comply with Eon
while True:
    h,t = dht.read_retry(dht.DHT22, 4)
    temp={0:0.1f}.format(t)
    hum={1:0.1f}.format(h)
    message = {'temperature': temp, 'humidity': hum}
    print 'Temp={0:0.1f}*C Humidity={1:0.1f}%'.format(t, h)
    pubnub.publish(channel=channel, message=message, callback=callback, error=callback)
