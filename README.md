# Humidity-Temp
code for the Humidity Temp application
    import os
    import time
    import sys
    from Pubnub import Pubnub
    import Adafruit_DHT as dht
    pubnub = Pubnub(pub-c-b3be2fd6-c0f8-4c79-b497-aa905ce31c5e,sub-c-0b58259a-7ee8-11e7-a47c-def805f681ee)
    channel = 'pi-house'
    temp='{0:0.1f}'.format(t)
    hum='{0:0.1f}'.format(h)
    message = {'temperature': temp, 'humidity': hum}
    pubnub.publish(channel=channel, message=message, callback=callback, error=callback)
