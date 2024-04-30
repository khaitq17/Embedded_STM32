# Embedded-Automotive

B�i 2: GPIO

1. C?p xung clock cho GPIO
S? d?ng c�c API ???c cung c?p s?n cho t?ng Bus. C�c ngo?i vi tr�n Bus ???c c?p xung th�ng qua vi?c truy?n c�c tham s? v�o API n�y.

Module RCC (Reset and Clock control) cung c?p c�c h�m ?? c?u h�nh xung clock.
RCC_APB2PeriphClockCmd(uint32_t RCC_APB2Periph, FunctionalState NewState);
RCC_APB2Periph: RCC_APB2Periph_GPIOA
                               RCC_APB2Periph_TIM2
                              RCC_APB2Periph_ADC1
                                           ���.
FunctionalState NewState: ENABLE or DISABLE
                           
2. C?u h�nh GPIO
2.1. C?u h�nh Pin GPIO
M?t ch�n trong GPIO c� th? ???c c?u h�nh th�ng qua struct GPIO_InitTypeDef g?m c�c th�ng s?:
GPIO_Pin: Ch?n Pin
GPIO_Mode: Ch?n Mode 
GPIO_Speed: T?c ?? ?�p ?ng
2.2. Kh?i t?o GPIO
H�m GPIO_Init() d�ng ?? kh?i t?o GPIO g?m 2 th�ng s?:
GPIO_TypeDef: GPIO c?n c?u h�nh
&GPIO_InitStruct: Con tr? t?i bi?n TypeDef v?a ???c t?o











3. C�c h�m GPIO th�ng d?ng 
??c gi� tr? 1 bit ch�n input
uint8_t GPIO_ReadInputDataBit(GPIO_TypeDef* GPIOx, uint16_t GPIO_Pin);

??c gi� tr? t?t c? c�c bit ch�n input 
uint16_t GPIO_ReadInputData(GPIO_TypeDef* GPIOx);

??c gi� tr? 1 bit ch�n output
uint8_t GPIO_ReadOutputDataBit(GPIO_TypeDef* GPIOx, uint16_t GPIO_Pin);

??c gi� tr? t?t c? c�c bit ch�n output
uint16_t GPIO_ReadOutputData(GPIO_TypeDef* GPIOx);

Set bit l�n m?c 1
void GPIO_SetBits(GPIO_TypeDef* GPIOx, uint16_t GPIO_Pin);

Reset bit v? m?c 0
void GPIO_ResetBits(GPIO_TypeDef* GPIOx, uint16_t GPIO_Pin);

Ghi gi� tr? cho 1 bit 
void GPIO_WriteBit(GPIO_TypeDef* GPIOx, uint16_t GPIO_Pin, BitAction BitVal);

Ghi gi� tr? cho 1 ch�n
void GPIO_Write(GPIO_TypeDef* GPIOx, uint16_t PortVal);



