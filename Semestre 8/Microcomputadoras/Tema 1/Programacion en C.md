Links: [[Temario Microprocesadores]]
___

PIC_C_Compiler

**CCS - C Compiler** -> Instalar
PCB, PCM, PCH


```c
#if defined (__PCB__)
#include <16C56.h>
#fuses HS,NOWDT,NOPROTECT,NOLVF
#use delay(clock=20000000)

#elif defined(__PCM__)
#include <16F877.h>
#fuses HS,NOWDT,NOPROTECT,NOLVF
#use delay(clock=20000000)
#endif

#elif defined(__PCH__)
#include <18F452.h>
#fuses HS,NOWDT,NOPROTECT,NOLVF
#use delay(clock=20000000)
#endif

```


CCS:
Programa para prender y apagar un LED
```CCS
#include <16F877.h>
#fuses HS,NOWDT,NOPROTECT,NOLVF
#use delay(clock=20000000) //20 Mhz

int main(void)
{
	while(TRUE)
	{
		OUTPUT_B(1); //Prende LED
		delay_ms(500); //Retardo de 500 milisegundos
		OUTPUT_B(0); //Apaga LED
		delay_ms(500); //Retardo de 500 milisegundos
		return 0;
	}
	
}
```

```ccs
main()
{
				 //b'pgfedcba'
	char numero = 0b10001000;
	unsigned int numeros[]={0b1100000, 0b10010100}
	char i = 0;
	
	for(;;){/loop infinito
		output_b(numeros[i++]);
		if(i == 1) i=0;
		delay_ms(500);
	}
}

```