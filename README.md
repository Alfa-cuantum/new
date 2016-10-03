#define _XTAL_FREQ 4000000
#include <stdio.h>
#include <htc.h>
#include "usart.h"

void main(void){

unsigned char input;
INTCON=0;	// purpose of disabling the interrupts.
TRISD=0;
init_comms();	// set up the USART - settings defined in usart.h

// Output a message to prompt the user for a keypress	
printf("\rPress a key and I will echo it back:\n");

while(1){
servonc:
servoc:
input = getch();	// read a response from the user
printf("\rI detected [%c]",input);	// echo it back
     
//TILT
if (input=='L')
{
PORTD=1;
__delay_ms(15);
PORTD=0;
__delay_ms(5);
goto servonc;
}
if (input=='R')
{
PORTD=1;
__delay_ms(.3);
PORTD=0;
__delay_ms(5);
goto servoc;
}
}
}
