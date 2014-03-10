int R = 9;
int G = 10;
int B = 11;
void setup() {
  setColor(0,0,0);
  attachInterupt(0, sameColor, CHANGE);
}

void sameColor()
{
  if (irrecv.decode(&results))
  {
    if (results.value==0x010)
    {
       setColor(255,0,0);
    }
    if (results.value==0x810)
    {
       setColor(255,255,0);
    }
    if (results.value==0x410)
    {
       setColor(255,0,255);
    }
    if (results.value==0xC10)
    {
       setColor(0,255,0);
    }
    if (results.value==0x210)
    {
       setColor(0,255,255);
    }
    if (results.value==0xA10)
    {
       setColor(0,0,255);
    }
    if (results.value==0x610)
    {
       rainbow;
    }
  } 
}

void rainbow ()
{
  int rgbColor[3];
 
  rgbColor[0] = 255;
  rgbColor[1] = 0;
  rgbColor[2] = 0;
  
  for (int i = 0; i < 3; i ++) 
  {
    int incColor = i == 2 ? 0 : i + 1;
 
    for(int o = 0; o < 255; o ++) 
    {
      rgbColor[i] -= 1;
      rgbColor[incColor] += 1;
    
      setColor(rgbColor[0], rgbColor[1], rgbColor[2]);
      delay(5);
    }
  }
}
  
void setColor(int red, int green, int blue) {
  analogWrite(R, red);
  analogWrite(G, green);
  analogWrite(B, blue);
}

void loop() 
{
  
}
