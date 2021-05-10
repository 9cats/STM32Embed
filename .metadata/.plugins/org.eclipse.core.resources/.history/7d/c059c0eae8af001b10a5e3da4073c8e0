// base.h⽂件
#ifndef __BASE_H
#define __BASE_H
#include "stdlib.h"
#include "stm32f1xx.h"
#include "stm32f1xx_hal.h"
#include "main.h"
#include "gpio.h"

// 定义可能会出现的兼容变量类型
#define u32 uint32_t
#define u16 uint16_t
#define u8 uint8_t
#define s32 int32_t
#define s16 int16_t
#define s8 int8_t

// LED电平设置 0-亮 1-灭
#define LED0(n) (n?HAL_GPIO_WritePin(LED0_GPIO_Port,LED0_Pin,GPIO_PIN_SET):HAL_GPIO_WritePin(LED0_GPIO_Port,LED0_Pin,GPIO_PIN_RESET))
#define LED0_T (HAL_GPIO_TogglePin(LED0_GPIO_Port, LED0_Pin))
#define LED0_ON LED0(0)
#define LED0_OFF LED0(1)
#define LED1(n) (n?HAL_GPIO_WritePin(LED1_GPIO_Port,LED1_Pin,GPIO_PIN_SET):HAL_GPIO_WritePin(LED1_GPIO_Port,LED1_Pin,GPIO_PIN_RESET))
#define LED1_T (HAL_GPIO_TogglePin(LED1_GPIO_Port, LED1_Pin))
#define LED1_ON LED1(0)
#define LED1_OFF LED1(1)

// 按键部分常用
// 不使用时注释
//#define KEY0 HAL_GPIO_ReadPin(KEY0_GPIO_Port,KEY0_Pin)//读取按键0
//#define KEY1 HAL_GPIO_ReadPin(KEY1_GPIO_Port,KEY1_Pin)//读取按键1
//#define KEY2 HAL_GPIO_ReadPin(KEY2_GPIO_Port,KEY2_Pin)//读取按键2
//#define KEY0_PRES 1
//#define KEY1_PRES 2
//#define KEY2_PRES 3
//u8 KEY_Scan(u8 mode); //按键扫描函数

// 自定义delay函数，兼容部分硬件库
void delay_init(u8 SYSCLK);
void delay_ms(u16 nms);
void delay_us(u32 nus);
void delay_ns (u8 t);


//IO⼝地址映射
#define BITBAND(addr, bitnum) ((addr & 0xF0000000)+0x2000000+((addr&0xFFFFF)<<5)+(bitnum<<2))
#define MEM_ADDR(addr) *((volatile unsigned long *)(addr))
#define BIT_ADDR(addr, bitnum) MEM_ADDR(BITBAND(addr, bitnum))
#define GPIOA_ODR_Addr    (GPIOA_BASE+12) //0x4001080C 
#define GPIOB_ODR_Addr    (GPIOB_BASE+12) //0x40010C0C 
#define GPIOC_ODR_Addr    (GPIOC_BASE+12) //0x4001100C 
#define GPIOD_ODR_Addr    (GPIOD_BASE+12) //0x4001140C 
#define GPIOE_ODR_Addr    (GPIOE_BASE+12) //0x4001180C 
#define GPIOF_ODR_Addr    (GPIOF_BASE+12) //0x40011A0C    
#define GPIOG_ODR_Addr    (GPIOG_BASE+12) //0x40011E0C    

#define GPIOA_IDR_Addr    (GPIOA_BASE+8) //0x40010808 
#define GPIOB_IDR_Addr    (GPIOB_BASE+8) //0x40010C08 
#define GPIOC_IDR_Addr    (GPIOC_BASE+8) //0x40011008 
#define GPIOD_IDR_Addr    (GPIOD_BASE+8) //0x40011408 
#define GPIOE_IDR_Addr    (GPIOE_BASE+8) //0x40011808 
#define GPIOF_IDR_Addr    (GPIOF_BASE+8) //0x40011A08 
#define GPIOG_IDR_Addr    (GPIOG_BASE+8) //0x40011E08 
//IO⼝操作,只对单⼀的IO⼝
//确保n的值⼩于16
#define PAout(n) BIT_ADDR(GPIOA_ODR_Addr,n) //输出
#define PAin(n) BIT_ADDR(GPIOA_IDR_Addr,n) //输⼊
#define PBout(n) BIT_ADDR(GPIOB_ODR_Addr,n) //输出
#define PBin(n) BIT_ADDR(GPIOB_IDR_Addr,n) //输⼊
#define PCout(n) BIT_ADDR(GPIOC_ODR_Addr,n) //输出
#define PCin(n) BIT_ADDR(GPIOC_IDR_Addr,n) //输⼊
#define PDout(n) BIT_ADDR(GPIOD_ODR_Addr,n) //输出
#define PDin(n) BIT_ADDR(GPIOD_IDR_Addr,n) //输⼊
#define PEout(n) BIT_ADDR(GPIOE_ODR_Addr,n) //输出
#define PEin(n) BIT_ADDR(GPIOE_IDR_Addr,n) //输⼊
#define PFout(n) BIT_ADDR(GPIOF_ODR_Addr,n) //输出
#define PFin(n) BIT_ADDR(GPIOF_IDR_Addr,n) //输⼊
#define PGout(n) BIT_ADDR(GPIOG_ODR_Addr,n) //输出
#define PGin(n) BIT_ADDR(GPIOG_IDR_Addr,n) //输⼊
#define PHout(n) BIT_ADDR(GPIOH_ODR_Addr,n) //输出
#define PHin(n) BIT_ADDR(GPIOH_IDR_Addr,n) //输⼊
#define PIout(n) BIT_ADDR(GPIOI_ODR_Addr,n) //输出
#define PIin(n) BIT_ADDR(GPIOI_IDR_Addr,n) //输⼊
#define PJout(n) BIT_ADDR(GPIOJ_ODR_Addr,n) //输出
#define PJin(n) BIT_ADDR(GPIOJ_IDR_Addr,n) //输⼊
#define PKout(n) BIT_ADDR(GPIOK_ODR_Addr,n) //输出
#define PKin(n) BIT_ADDR(GPIOK_IDR_Addr,n) //输⼊
#endif
