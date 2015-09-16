#include <Keypad.h>

const byte ROWS = 11; //eleven rows
const byte COLS = 8; //eight columns
int keys[ROWS][COLS] ={
  {0, 1, 2, 3, 4, 5, 6, 7},
  {8, 9, 10, 11, 12, 13, 14, 15},
  {16, 17, 18, 19, 20, 21, 22, 23},
  {24, 25, 26, 27, 28, 29, 30, 31},
  {32, 33, 34, 35, 36, 37, 38, 39},
  {40, 41, 42, 43, 44, 45, 46, 47},
  {48, 49, 50, 51, 52, 53, 54, 55},
  {56, 57, 58, 59, 60, 61, 62, 63},
  {64, 65, 66, 67, 68, 69, 70, 71},
  {72, 73, 74, 75, 76, 77, 78, 79},
  {80, 81, 82, 83, 84, 85, 86, 87},
  };
byte rowPins[ROWS] = {2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12}; //connect to the row pinouts of the keypad
byte colPins[COLS] = {13, A0, A1, A2, A3, A4, A5}; //connect to the column pinouts of the keypad

Keypad keypad = Keypad( makeKeymap(keys), rowPins, colPins, ROWS, COLS );

void setup(){
  Serial.begin(9600);
}

void loop(){
  int key = keypad.getKey();

  if (key != NO_KEY){
    Serial.println(key);
  }
}
