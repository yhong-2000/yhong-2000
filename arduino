#include <Servo.h> 

Servo servo;    //create servo object to control a servo
int n;
int AnalogValue1;
int AnalogValue2;
int Diff1;
int Diff2;

void setup() 
{
  pinMode(8,INPUT);   //assign digital pin 8 as LDR1 input
  pinMode(10,INPUT);  //assign digital pin 8 as LDR2 input
  servo.attach(3);    //servo is wired to Arduino on digital pin 3
  Serial.begin(9600); //initialise serial monitor
  n=90;
}

void loop() 
{
  /*assign digital and analog value of LDR sensors*/
  int AnalogValue1 = analogRead(A0); 
  int AnalogValue2 = analogRead(A1);   

  int Diff1 = AnalogValue1-AnalogValue2;
  int Diff2 = AnalogValue2-AnalogValue1;
  
  /*display output on serial monitor*/     
  Serial.println("Diff1:");   
  Serial.println(Diff1);        
  Serial.println("Diff2:");   
  Serial.println(Diff2);        

  /*control the angle n based on LDR value*/
  if ((AnalogValue1 > 900) && (AnalogValue2 > 900))
  {
    n=90;
  }
  else if (Diff1>20)
  {  
    n=n+1;
  }
  else if (Diff2>20)
  {
    n=n-1;
  }
  else
  {
    n=n; 
  }

  Serial.println("The angle now is");
  Serial.println(n);
  
  /*move servo's shaft to angle n°*/
  servo.write(n);
  delay(20);                         
}
