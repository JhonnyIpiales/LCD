# LCD
PASSWORD
#include <LiquidCrystal.h>
LiquidCrystal lcd (12, 11, 5, 4, 3, 2); 
int cont=0;
String incomingByte;

void setup() {
  
  lcd.begin(16,2);
  Serial.begin(9600);
  Serial.println("Ingresar La Contraseña");
  lcd.clear();
}

void loop() {
 
if (Serial.available() > 0) {
      incomingByte = Serial.readString();
      Serial.print("He recibido: "); 
      Serial.println("*");
      lcd.setCursor(0,0);  
      if(incomingByte.equals("Jose") ){//Clave correcta
        lcd.clear();
        lcd.print("CLAVE CORRECTA");
      }
      else{
        lcd.clear();//Clave incorrecta
        lcd.print("CLAVE INCORRECTA");
      }
   }
}
