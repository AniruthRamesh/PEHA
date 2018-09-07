int ir1=7;
int ir2=8;
int led1=13;
int buzzer = 12;
int count = 0;
void setup() {
  Serial.begin(9600);
  pinMode(ir1,INPUT);
  pinMode(ir2,INPUT);
  pinMode(buzzer,OUTPUT);
  pinMode(led1,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
if(digitalRead(ir1)==HIGH)
{
  tone(buzzer,6000,100);
  count+=1;
  Serial.println(count);
  
}

if(digitalRead(ir2)== HIGH)
 {
  tone(buzzer,250,100);
  count-=1; 
  Serial.println(count);
 }
 if(count>=1)
 {
  digitalWrite(led1,HIGH);
 }
 if(count<=0)
 {
  count = 0;
  digitalWrite(led1,LOW);
  
  }
  delay(500);
 }
