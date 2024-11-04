# Interfacing a 4x4 matrix keypad

## Aim: 
To simulate the interface of a 4x4 matrix keypad to ARM controller and display the output on 16X2 LCD for arithmetic operation only.

## Components required: 
STM32 CUBE IDE, Proteus 8 simulator .

## Keypad layout

![image](https://github.com/user-attachments/assets/c24e7e27-7b0f-4904-becd-307fbf7dcba8)


## CIRCUIT DIAGRAM 
![image](https://github.com/user-attachments/assets/596c321a-9baf-477b-beec-5244738afbf8)

## Program
### Header files
#include "main.h"

#include <stdbool.h>

#include "lcd.h"

### Variables declaration
bool col1,col2,col3,col4;

### Functions declaration
void SystemClock_Config(void);

static void MX_GPIO_Init(void);

void key();

### User defined function definition
void key()

{

 ### Initialize the input and output pins of the keypad

  ---------

  ---------
 
  
  if(!col1)
	
  {
	
     Lcd_cursor(&lcd, 0,1);
	 	 
     Lcd_string(&lcd, " -------\n");
	 	 
     HAL_Delay(500);
	 
  }
	
  else if(!col2)
	
  {
	
     Lcd_cursor(&lcd, 0,1);
	 	 
     Lcd_string(&lcd, "--------\n");
	   
     HAL_Delay(500);
	 
  }
	
  else if(!col3)
	
  {
	
     Lcd_cursor(&lcd, 0,1);
	 	 
     Lcd_string(&lcd, "--------\n");
	  
    HAL_Delay(500);
	 
  }
	
  else if(!col4)
	
  {
	
     Lcd_cursor(&lcd, 0,1);
	 	 
     Lcd_string(&lcd, "--------\n");
	   
     HAL_Delay(500);
	 
  }
	
  HAL_Delay(100);

}

### Main function

int main(void)

{

  HAL_Init();
  
  SystemClock_Config();
  
  MX_GPIO_Init();
  
  Lcd_PortType ports[] = { GPIOA, GPIOA, GPIOA, GPIOA };
	
 Lcd_PinType pins[] = {GPIO_PIN_3, GPIO_PIN_2, GPIO_PIN_1, GPIO_PIN_0};

 Lcd_HandleTypeDef lcd;

 lcd = Lcd_create(ports, pins, GPIOB, GPIO_PIN_0, GPIOB, GPIO_PIN_1, LCD_4_BIT_MODE);
 
   while (1)
   
    {
  
  ### function call
  
    key();
	 
  }

}

## Output screen shots of proteus
![image](https://github.com/user-attachments/assets/d694bfa1-a722-4ec9-bd43-8893c3e5518c)

## Result :
Thus,Interfaced a 4x4 matrix keypad with ARM microcontroller and displayed the output on 16X2 LCD in simulation successfully.
