# Codigo-Display-y-ALU-.
int Op1 = 0;
int Op2 = 0;
int Op3 = 0;
int Op4 = 0;

int a = 9;
int b = 8;
int c = 7;
int d = 6;
int e = 5;
int f = 4;
int g = 3;

void setup() {
  pinMode(13, INPUT); //Op1
  pinMode(12, INPUT); //Op2
  pinMode(11, INPUT); //Op3
  pinMode(10, INPUT); //Op4

  pinMode(a, OUTPUT); //A
  pinMode(b, OUTPUT); //B
  pinMode(c, OUTPUT); //C
  pinMode(d, OUTPUT); //D
  pinMode(e, OUTPUT); //E
  pinMode(f, OUTPUT); //F
  pinMode(g, OUTPUT); //G
  
  Serial.begin(9600);
}

void loop() {
  Op1 = digitalRead(13);
  Op2 = digitalRead(12);
  Op3 = digitalRead(11);
  Op4 = digitalRead(10);

  int numero = 0; 

  
  if (!Op4 && !Op3 && !Op2 && Op1) { numero = 1; }   
  else if (!Op4 && !Op3 && Op2 && !Op1) { numero = 2; } 
  else if (!Op4 && !Op3 && Op2 && Op1) { numero = 3; }
  else if (!Op4 && Op3 && !Op2 && !Op1) { numero = 4; }    
  else if (!Op4 && Op3 && !Op2 && Op1) { numero = 5; } 
  else if (!Op4 && Op3 && Op2 && !Op1) { numero = 6; } 
  else if (!Op4 && Op3 && Op2 && Op1) { numero = 7; }
  else if (Op4 && !Op3 && !Op2 && !Op1) { numero = 8; } 
  else if (Op4 && !Op3 && !Op2 && Op1) { numero = 9; }
 else if (Op4 && !Op3 && Op2 && !Op1) { numero = 10; }  // A
  else if (Op4 && !Op3 && Op2 && Op1) { numero = 11; }   // B
  else if (Op4 && Op3 && !Op2 && !Op1) { numero = 12; }  // C
  else if (Op4 && Op3 && !Op2 && Op1) { numero = 13; }   // D
  else if (Op4 && Op3 && Op2 && !Op1) { numero = 14; }   // E
  else if (Op4 && Op3 && Op2 && Op1) { numero = 15; }    // F

 

  if (numero == 0) { 
    numero = 0; 
  }

  mostrarNumero(numero); 
}

void apagarDisplay() {
  digitalWrite(a, LOW);
  digitalWrite(b, LOW);
  digitalWrite(c, LOW);
  digitalWrite(d, LOW);
  digitalWrite(e, LOW);
  digitalWrite(f, LOW);
  digitalWrite(g, LOW);
}


void mostrarNumero(int numero) {
  apagarDisplay(); 

  switch (numero) {
    case 0:
      digitalWrite(a, HIGH);
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(f, HIGH);
      break;
    case 1:
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      break;
    case 2:
      digitalWrite(a, HIGH);
      digitalWrite(b, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 3:
      digitalWrite(a, HIGH);
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 4:
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 5:
      digitalWrite(a, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 6:
      digitalWrite(a, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 7:
      digitalWrite(a, HIGH);
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      break;
    case 8:
      digitalWrite(a, HIGH);
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 9:
      digitalWrite(a, HIGH);
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 10: // A
      digitalWrite(a, HIGH);
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 11: // B
      digitalWrite(c, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 12: // C
      digitalWrite(a, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(f, HIGH);
      break;
    case 13: // D
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 14: // E
      digitalWrite(a, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    case 15: // F
      digitalWrite(a, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      break;
    
  }
}
