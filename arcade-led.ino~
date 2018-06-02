/*
  Arcade LED button effects
  Rodrigo Feliciano
  https://www.pakequis.com.br
  youtube.com/pakequis

*/

#include <SoftPWM.h>  //library: https://github.com/bhagman/SoftPWM

//LED OFF to ON time (ms)
#define FADE_IN   50
//LED ON to OFF time (ms)
#define FADE_OUT  1000
//Number of Buttons and LED Channels
#define N_CHANNELS  8

/******************************/
/* Arduino Uno R3             */
//Buttons pins:
//#define BT1  A0
//#define BT2  A1
//#define BT3  A2
//#define BT4  A3
//#define BT5  A4
//#define BT6  A5
//#define BT7  1
//#define BT8  2

//LED pins
//#define LED1  3
//#define LED2  4
//#define LED3  5
//#define LED4  6
//#define LED5  7
//#define LED6  8
//#define LED7  9
//#define LED8  10
/******************************/

/******************************/
/* Arduino Mini Pro           */
//Buttons pins:
#define BT1  A3
#define BT2  A2
#define BT3  A1
#define BT4  A0
#define BT5  13
#define BT6  12
#define BT7  11
#define BT8  10

//LED pins
#define LED1  2
#define LED2  3
#define LED3  4
#define LED4  5
#define LED5  6
#define LED6  7
#define LED7  8
#define LED8  9
/******************************/

int b[N_CHANNELS] = {BT1,BT2,BT3,BT4,BT5,BT6,BT7,BT8};
int LED[N_CHANNELS] = {LED1,LED2,LED3,LED4,LED5,LED6,LED7,LED8};
int i = 0;

void setup()
{
  SoftPWMBegin();

  for (i = 0; i < N_CHANNELS; i++)
  {
    SoftPWMSet(LED[i],0);
    SoftPWMSetFadeTime(LED[i], FADE_IN, FADE_OUT);
    pinMode(b[i],INPUT);
  }

  pinMode(0,INPUT);
}

void loop()
{
  for(i = 0; i < N_CHANNELS; i++)
  {
    if(!digitalRead(b[i]))
    {
      SoftPWMSet(LED[i], 0);  
    }else
    {
      SoftPWMSet(LED[i], 255);
    }
  }  
}

