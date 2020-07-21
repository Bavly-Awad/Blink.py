Import Rpi as GPIO
import time

ledPin = 11

def setup():
       GPIO.setmode(GPIO.BOARD)
       GPIO.setup(ledPin, GPIO.OUT)
       GPIO.output(ledPin, GPIO.LOW)


def loop():
      while true:
              GPIO.output(ledPin, GPIO.HIGH)
               print (‘Led Turned On >>>’)
               time.sleep(1)
               GPIO.output(ledPin, GPIO.LOW)
               print (‘Led Turned Off <<<’)
               time.sleep(1)

def destroy():
       GPIO.cleanup()

if name == ‘_main_’:
   print ('Program is starting ... \n')
   setup()
   try:
        loop()
   except KeyboardInterrupt:
        destroy()
