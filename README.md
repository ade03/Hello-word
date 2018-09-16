#include <Wire.h>  // Comes with Arduino IDE
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd1(0x27, 2, 1, 0, 4, 5, 6, 7, 3, POSITIVE); 
// Specify the 1st I2C chip address used for 1st LCD & its connection pins
// (addr, en,rw,rs,d4,d5,d6,d7,bl,blpol);

LiquidCrystal_I2C lcd2(0x26, 2, 1, 0, 4, 5, 6, 7, 3, POSITIVE); 
// Specify the 2nd I2C chip address used for 2nd LCD & its connection pins
// (addr, en,rw,rs,d4,d5,d6,d7,bl,blpol);


void setup()   
{
  Serial.begin(9600);

  lcd1.begin(16,2);   // initialize the 1st lcd for 16 chars 2 lines, turn on backlight
  lcd2.begin(16,2);   // initialize the 2nd lcd for 16 chars 2 lines, turn on backlight

//-------- Write characters on the 1st & 2nd displays ------------------
 // NOTE: Cursor Position: (CHAR, LINE) start at 0 
  lcd1.setCursor(0,0);
  lcd1.print("Hello, world!");
  lcd2.setCursor(0,0);
  lcd2.print("Hello, world!");
  delay(2000);
  lcd1.setCursor(0,1);
  lcd1.print("I'm 1st 16x2LCD");
  lcd2.setCursor(0,1); 
  lcd2.print("I'm 2nd 16x2LCD");
}


void loop()   
{
 }
