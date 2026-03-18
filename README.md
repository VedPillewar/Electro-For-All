# Electro-For-All
This are the code which any beginner can use for starting and getting boost in his programming career in electronic domain making any electronic model or iot project or something. This code are fre to use and any body can use to code for learn basic and use them in complex project .


[1]|[A] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- LED blinking program.

CODE NO :- 1

    #define LED 13

    void setup()
    {
    pinMode(LED,OUTPUT);
    }

    void loop()
    {
    digitalWrite(LED,HIGH);
    delay(1000);
    digitalWrite(LED,LOW);
    delay(1000);
    }

[2]|[B] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- LED control using push button.

CODE NO :- 2

    #define LED 13
    #define SW 7

    void setup()
    {
    pinMode(LED,OUTPUT);
    pinMode(SW,INPUT);
    }

    void loop()
    {
    int val=digitalRead(SW);

    if(val==HIGH)
    digitalWrite(LED,HIGH);
    else
    digitalWrite(LED,LOW);
    }

[3]|[C] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- Buzzer ON/OFF.

CODE NO :- 3

    #define BUZ 8

    void setup()
    {
    pinMode(BUZ,OUTPUT);
    }

    void loop()
    {
    digitalWrite(BUZ,HIGH);
    delay(1000);
    digitalWrite(BUZ,LOW);
    delay(1000);
    }

[4]|[D] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- LDR sensor with LED.

CODE NO :- 4

    int ldr=A0;
    int led=13;
 
    void setup()
    {
    pinMode(led,OUTPUT);
    }

    void loop()
    {
    int val=analogRead(ldr);

    if(val<500)
    digitalWrite(led,HIGH);
    else
    digitalWrite(led,LOW);
    }

[5]|[E] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- Servo motor control.

CODE NO :- 5

    #include <Servo.h>

    Servo s;

    void setup()
    {
    s.attach(9);
    }

    void loop()
    {
    s.write(0);
    delay(1000);
    s.write(90);
    delay(1000);
    s.write(180);
    delay(1000);
    }

[6]|[F] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- DC motor control using L298N.

CODE NO :- 6

    #define IN1 8
    #define IN2 9

    void setup()
    {
    pinMode(IN1,OUTPUT);
    pinMode(IN2,OUTPUT);
    }

    void loop()
    {
    digitalWrite(IN1,HIGH);
    digitalWrite(IN2,LOW);
    delay(3000);

    digitalWrite(IN1,LOW);
    digitalWrite(IN2,LOW);
    delay(2000);
    }

[7]|[G] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- Ultrasonic sensor distance.

CODE NO :- 7

    int trig=9;
    int echo=10;

    void setup()
    {
    Serial.begin(9600);
    pinMode(trig,OUTPUT);
    pinMode(echo,INPUT);
    }

    void loop()
    {
    digitalWrite(trig,LOW);
    delayMicroseconds(2);
    digitalWrite(trig,HIGH);
    delayMicroseconds(10);
    digitalWrite(trig,LOW);

    long duration=pulseIn(echo,HIGH);
    int dist=duration*0.034/2;

    Serial.println(dist);
    delay(1000);
    }

[8]|[H] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- IR sensor with LED.

CODE NO :- 8

    int ir=7;
    int led=13;

    void setup()
    {
    pinMode(ir,INPUT);
    pinMode(led,OUTPUT);
    }

    void loop()
    {
    if(digitalRead(ir)==0)
    digitalWrite(led,HIGH);
    else
    digitalWrite(led,LOW);
    }

[9]|[I] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- Potentiometer LED brightness.

CODE NO :- 9

    int pot=A0;
    int led=9;
    
    void setup()
    {
        pinMode(led,OUTPUT);
    }
    
    void loop()
    {
        int val=analogRead(pot);
        val=val/4;
        analogWrite(led,val);
    }

[10]|[J] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- Temperature sensor (LM35).

CODE NO :- 10

    int temp=A0;
    
    void setup()
    {
        Serial.begin(9600);
    }
    
    void loop()
    {
        int val=analogRead(temp);
        float t=val*0.488;
    
        Serial.println(t);
        delay(1000);
    }

[11]|[K] LANGUAGE:- "C"

HARDWARE BOARD:-"ESP32"

PROBLEM STATEMENT:- LED blinking.

CODE NO :- 11

    int led=2;
    
    void setup()
    {
        pinMode(led,OUTPUT);
    }
    
    void loop()
    {
        digitalWrite(led,HIGH);
        delay(1000);
        digitalWrite(led,LOW);
        delay(1000);
    }

[12]|[L] LANGUAGE:- "C"

HARDWARE BOARD:-"ESP32"

PROBLEM STATEMENT:- Touch sensor with LED.

CODE NO :- 12

    int led=2;
    
    void setup()
    {
        pinMode(led,OUTPUT);
    }
    
    void loop()
    {
        int val=touchRead(4);
    
        if(val<30)
        digitalWrite(led,HIGH);
        else
        digitalWrite(led,LOW);
    }

[13]|[M] LANGUAGE:- "C"

HARDWARE BOARD:-"ESP32"

PROBLEM STATEMENT:- Buzzer control.

CODE NO :- 13

    int buz=15;
    
    void setup()
    {
        pinMode(buz,OUTPUT);
    }
    
    void loop()
    {
        digitalWrite(buz,HIGH);
        delay(500);
        digitalWrite(buz,LOW);
        delay(500);
    }

[14]|[N] LANGUAGE:- "Python"

HARDWARE BOARD:-"Raspberry Pi 4/5"

PROBLEM STATEMENT:- LED blinking.

CODE NO :- 14

    import RPi.GPIO as GPIO
    import time
    
    LED=18
    
    GPIO.setmode(GPIO.BCM)
    GPIO.setup(LED,GPIO.OUT)
    
    while True:
        GPIO.output(LED,True)
        time.sleep(1)
        GPIO.output(LED,False)
        time.sleep(1)

[15]|[O] LANGUAGE:- "Python"

HARDWARE BOARD:-"Raspberry Pi 4/5"

PROBLEM STATEMENT:- Button with LED.

CODE NO :- 15
    
    import RPi.GPIO as GPIO
    
    LED=18
    SW=23
    
    GPIO.setmode(GPIO.BCM)
    GPIO.setup(LED,GPIO.OUT)
    GPIO.setup(SW,GPIO.IN)
    
    while True:
        if GPIO.input(SW)==1:
            GPIO.output(LED,True)
        else:
            GPIO.output(LED,False)

[16]|[P] LANGUAGE:- "Python"

HARDWARE BOARD:-"Raspberry Pi 4/5"

PROBLEM STATEMENT:- Buzzer control.

CODE NO :- 16

    import RPi.GPIO as GPIO
    import time
    
    BUZ=18
    
    GPIO.setmode(GPIO.BCM)
    GPIO.setup(BUZ,GPIO.OUT)
    
    while True:
        GPIO.output(BUZ,True)
        time.sleep(1)
        GPIO.output(BUZ,False)
        time.sleep(1)

[17]|[Q] LANGUAGE:- "Python"

HARDWARE BOARD:-"Raspberry Pi 4/5"

PROBLEM STATEMENT:- LDR sensor.

CODE NO :- 17

    from gpiozero import LightSensor
    from time import sleep
    
    ldr=LightSensor(4)
    
    while True:
        print(ldr.value)
        sleep(1)
    
  [18]|[R] LANGUAGE:- "Python"
  
  HARDWARE BOARD:-"Raspberry Pi 4/5"
  
  PROBLEM STATEMENT:- Ultrasonic sensor.

CODE NO :- 18

    import RPi.GPIO as GPIO
    import time
    
    TRIG=23
    ECHO=24
    
    GPIO.setmode(GPIO.BCM)
    GPIO.setup(TRIG,GPIO.OUT)
    GPIO.setup(ECHO,GPIO.IN)
    
    while True:
        GPIO.output(TRIG,True)
        time.sleep(0.00001)
        GPIO.output(TRIG,False)
    
        while GPIO.input(ECHO)==0:
            pass
        start=time.time()
    
        while GPIO.input(ECHO)==1:
            pass
        stop=time.time()
    
        dist=(stop-start)*34300/2
        print(dist)

[19]|[S] LANGUAGE:- "Python"

HARDWARE BOARD:-"Raspberry Pi 4/5"

PROBLEM STATEMENT:- Servo motor control.

CODE NO :- 19

    import RPi.GPIO as GPIO
    import time
    
    pin=18
    
    GPIO.setmode(GPIO.BCM)
    GPIO.setup(pin,GPIO.OUT)
    
    pwm=GPIO.PWM(pin,50)
    pwm.start(0)
    
    while True:
        pwm.ChangeDutyCycle(2.5)
        time.sleep(1)
        pwm.ChangeDutyCycle(12.5)
        time.sleep(1)

[20]|[T] LANGUAGE:- "Python"

HARDWARE BOARD:-"Raspberry Pi 4/5"

PROBLEM STATEMENT:- Relay control.

CODE NO :- 20

    import RPi.GPIO as GPIO
    import time
    
    RELAY=18
    
    GPIO.setmode(GPIO.BCM)
    GPIO.setup(RELAY,GPIO.OUT)
    
    while True:
        GPIO.output(RELAY,True)
        time.sleep(2)
        GPIO.output(RELAY,False)
        time.sleep(2)

[21]|[U] LANGUAGE:- "C"

HARDWARE BOARD:-"ESP32"

PROBLEM STATEMENT:- Relay control.

CODE NO :- 21
    
    int relay=5;
    
    void setup()
    {
        pinMode(relay,OUTPUT);
    }
    
    void loop()
    {
        digitalWrite(relay,HIGH);
        delay(2000);
        digitalWrite(relay,LOW);
        delay(2000);
    }

[22]|[V] LANGUAGE:- "C"

HARDWARE BOARD:-"ESP32"

PROBLEM STATEMENT:- IR sensor.

CODE NO :- 22

    int ir=15;
    int led=2;
    
    void setup()
    {
        pinMode(ir,INPUT);
        pinMode(led,OUTPUT);
    }
    
    void loop()
    {
        if(digitalRead(ir)==0)
        digitalWrite(led,HIGH);
        else
        digitalWrite(led,LOW);
    }

[23]|[W] LANGUAGE:- "C"

HARDWARE BOARD:-"ESP32"

PROBLEM STATEMENT:- PWM LED control.

CODE NO :- 23

    int led=2;
    
    void setup()
    {
        ledcSetup(0,5000,8);
        ledcAttachPin(led,0);
    }
    
    void loop()
    {
        for(int i=0;i<255;i++)
        {
            ledcWrite(0,i);
            delay(10);
        }
    }

[24]|[X] LANGUAGE:- "C"

HARDWARE BOARD:-"Arduino Uno"

PROBLEM STATEMENT:- Multiple LED sequence.

CODE NO :- 24
    
    int led1=8;
    int led2=9;
    int led3=10;
    
    void setup()
    {
        pinMode(led1,OUTPUT);
        pinMode(led2,OUTPUT);
        pinMode(led3,OUTPUT);
    }
    
    void loop()
    {
        digitalWrite(led1,HIGH);
        delay(500);
        digitalWrite(led1,LOW);
    
        digitalWrite(led2,HIGH);
        delay(500);
        digitalWrite(led2,LOW);
    
        digitalWrite(led3,HIGH);
        delay(500);
        digitalWrite(led3,LOW);
    }

[25]|[Y] LANGUAGE:- "Python"

HARDWARE BOARD:-"Raspberry Pi 4/5"

PROBLEM STATEMENT:- Gas sensor with buzzer.

CODE NO :- 25

    from gpiozero import DigitalInputDevice, Buzzer
    from time import sleep
    
    gas=DigitalInputDevice(17)
    buz=Buzzer(18)
    
    while True:
        if gas.value==0:
            buz.on()
        else:
            buz.off()
        sleep(1)
