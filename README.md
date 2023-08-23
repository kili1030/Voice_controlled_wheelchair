#include <AFMotor.h>
AF_DCMotor motor1(1);
AF_DCMotor motor2(2);
AF_DCMotor motor3(3);
AF_DCMotor motor4(4);
void setup()
{
Serial.begin(9600);
}
char c;
String voice;
void loop()
{
if (Serial.available()>0)
{
voice="";
voice=Serial.readString();  
Serial.print(voice+'\n');  
}     
if(voice=="forward")  
{     
motor2.setSpeed(240);  
motor1.setSpeed(240); 
motor2.run(BACKWARD); 
motor1.run(BACKWARD); 
motor3.setSpeed(240);
motor4.setSpeed(240);
motor3.run(BACKWARD); 
motor4.run(BACKWARD);
    }  
    else if(voice=="halt")  
    {    
    motor2.setSpeed(200);   
    motor1.setSpeed(200);  
    motor2.run(RELEASE);  
    motor1.run(RELEASE);
    motor3.setSpeed(200);  
    motor4.setSpeed(200);   
    motor3.run(RELEASE);   
    motor4.run(RELEASE);    
    }     
    else if(voice=="right")  
    {    
    motor2.setSpeed(200);  
    motor1.setSpeed(240);  
    motor2.run(RELEASE);   
    motor1.run(BACKWARD);   
    motor3.setSpeed(200);   
    motor4.setSpeed(240);   
    motor3.run(FORWARD);   
    motor4.run(BACKWARD);  
    }   
    else if(voice=="left")    
    {    
    motor2.setSpeed(240);  
    motor1.setSpeed(200);  
    motor2.run(BACKWARD);   
    motor1.run(RELEASE);  
    motor3.setSpeed(240);  
    motor4.setSpeed(200);   
    motor3.run(BACKWARD); 
    motor4.run (FORWARD);
    }
    else  if(voice=="backward")
    { 
    motor2.setSpeed(200)
  ; motor1.setSpeed(200);
  motor2.run(FORWARD);
  motor1.run(FORWARD); 
  motor3.setSpeed(200); 
  motor4.setSpeed(200);
  motor3.run(FORWARD); 
  motor4.run(FORWARD
  }
  }
  
