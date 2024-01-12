# Interfaz entre C y Assembler

El programa actúa como una interfaz entre C y ensamblador para obtener cotizaciones de criptomonedas y conversiones de divisas. Utiliza las APIs CoinLayer y Fixer para obtener información en tiempo real sobre las cotizaciones de Bitcoin (BTC) y Ethereum (ETH) en Dólares Estadounidenses (USD), así como el cambio de valor entre Dólar Estadounidense (USD) y Pesos Argentinos (ARS) y Euros (EUR).

### **¿Cómo usar?**
Puede clonar y compilar este repositorio siguiendo estos pasos:

```bash
$ git clone https://github.com/francobottini99/PR-INTFCASM-2023.git

$ cd PR-INTFCASM-2023

$ cmake .

$ make
```

Finalmente, para ejecutar el programa:

```bash
$ ./bin/TP2
```

>[!NOTE]
> Para poder utilizar las APIs, es necesario contar con una clave de acceso. en el archivo `include/main.h` debe modificar el valor de la variable `const char *coinlayer_path = "/live?access_key=TU_CLAVE";`.

### **Resumen del Funcionamiento**
Para el desarrollo de este programa se utilizaron las siguientes APIs:

* [CoinLayer](https://coinlayer.com/)
* [Fixer](https://fixer.io/)

La primera utilizada para obtener la cotización de las criptomonedas Bitcoin (BTC) y Ethereum (ETH) en Dólares Estadounidenses (USD) y en tiempo real, la segunda, para obtener el cambio de valor de divisas, de Dólar Estadounidense (USD) a Pesos Argentinos (ARS) y Euros (EUR).  

Al iniciar el programa, se realiza una consulta a las APIs, las cuales nos devuelven la información en formato JSON, posteriormente, extraemos los datos necesarios y los guardamos en estructuras.  
Luego, realizamos un par de llamadas a una función en assembler, la cual recibe como parámetro la cotización de la criptomoneda en Dólares Estadounidenses (USD) y el factor de conversión a la moneda deseada. Esta función, realiza la conversión de divisas y devuelve el resultado. De esta manera, obtenemos la cotización de Bitcoin (BTC) y Ethereum (ETH) en Pesos Argentinos (ARS) y Euros (EUR).