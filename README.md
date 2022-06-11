# TP2-Embebidos-GPIO
En este repo se encuentran las librerias para el manejos de los GPIO de la EDU CIAA.

Para ello se copiaron los archivos ´sapi_gpio.c´ ubicado en el path: ´C:\CIAA\firmware_v3\libs\sapi\sapi_v0.5.2\soc\peripherals\src´ y ´sapi_gpio.h´ ubicado en el path ´C:\CIAA\firmware_v3\libs\sapi\sapi_v0.5.2\soc\peripherals\inc´ y se los renombro por ´my_sapi_gpio.c´ y ´my_sapi_gpio.h´ ubicandolo en los mismos directorios donde se encontraban los archivos originales.

En la nueva libreria se definieron las funciones:
```
-bool_t mygpioInit( gpioMap_t pin, my_gpioInit_t config );
-bool_t mygpioRead( gpioMap_t pin );
-bool_t mygpioWrite( gpioMap_t pin, bool_t value );
-bool_t mygpioToggle( gpioMap_t pin );
```

Las estructuras:
```
typedef struct {
   pinInitLpc4337_t pinName;
   int8_t func;
   my_gpioInitLpc4337_t gpio;
} my_pinInitGpioLpc4337_t;

typedef struct {
   int8_t port;
   int8_t pin;
} my_gpioInitLpc4337_t;
```
y los tipos enumerativos
```
typedef enum {
   myGPIO_INPUT, myGPIO_OUTPUT,
   myGPIO_INPUT_PULLUP, myGPIO_INPUT_PULLDOWN,
   myGPIO_INPUT_PULLUP_PULLDOWN,
   myGPIO_ENABLE
} my_gpioInit_t;
```
