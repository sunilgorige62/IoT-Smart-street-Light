# IoT-Smart-street-Light
int IR1 = 8;
int IR2 = 12;
int LDR = 7;
int led1 = 3;
int led2 = 5;
int val1;
int val2;
int val3;

void setup()
{
  pinMode(IR1, INPUT);
  pinMode(IR2, INPUT);
  pinMode(LDR, INPUT);
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
}

void loop()
{
  val1 = digitalRead(IR1);
  val2 = digitalRead(IR2);
  val3 = digitalRead(LDR);

  if (val1 == 1 && val2 == 1 && val3 == 0)
  {
    digitalWrite(led1, LOW);
    digitalWrite(led2, LOW);
  }
  else if (val1 == 1 && val2 == 1 && val3 == 1)
  {
    analogWrite(led1, 20);
    analogWrite(led2, 20);
  }
  else if (val1 == 0 && val2 == 0 && val3 == 1)
  {
    analogWrite(led1, 500);
    analogWrite(led2, 500);
  }
  else if (val1 == 0 && val2 == 1 && val3 == 1)
  {
    analogWrite(led1, 500);
    analogWrite(led2, 20);
  }
  else if (val1 == 1 && val2 == 0 && val3 == 1)
  {
    analogWrite(led1, 20);
    analogWrite(led2, 500);
  }
  else if (val1 == 1 && val2 == 1 && val3 == 0)
  {
    analogWrite(led1, 20);
    analogWrite(led2, 20);
  }
}
