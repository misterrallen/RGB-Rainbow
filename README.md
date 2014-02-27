RGB-Rainbow
===========
#include <IRremote.h>

int R = 9;
int G = 10;
int B = 11;
int num = 0;
void setup() {
  setColor(0,0,0);
}
 
void loop() {
  int rgbColor[3];
 
  rgbColor[0] = 255;
  rgbColor[1] = 0;
  rgbColor[2] = 0;
  while (nume == 0)
  {
    for (int i = 0; i < 3; i ++) {
      int incColor = i == 2 ? 0 : i + 1;
 
      for(int o = 0; o < 255; o ++) {
        rgbColor[i] -= 1;
        rgbColor[incColor] += 1;
      
        setColor(rgbColor[0], rgbColor[1], rgbColor[2]);
        delay(5);
      }
    }
    if (irrecv.decode(&results)
    {
      num = 1;
    }
    else
    { 
      num = 0;
    }
  }
}
 
void setColor(int red, int green, int blue) {
  analogWrite(R, red);
  analogWrite(G, green);
  analogWrite(B, blue);
