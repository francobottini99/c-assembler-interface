# C and Assembly Interface

This program serves as an interface between C and Assembly to retrieve cryptocurrency quotes and currency conversions. It uses the CoinLayer and Fixer APIs to obtain real-time data on Bitcoin (BTC) and Ethereum (ETH) quotes in United States Dollars (USD), as well as exchange rates between USD and Argentine Pesos (ARS) and Euros (EUR).

### Authors:
- **Franco Nicolas Bottini**
- **Valentin Robledo**
- **Aquiles Benjamín Lencina**

### **How to Use**
Clone and compile this repository by following these steps:

```bash
$ git clone https://github.com/francobottini99/PR-INTFCASM-2023.git

$ cd PR-INTFCASM-2023

$ cmake .

$ make
```

Finally, to run the program:

```bash
$ ./bin/TP2
```

>[!NOTE]
> To use the APIs, an access key is required. In the file `include/main.h`, modify the value of the variable `const char *coinlayer_path = "/live?access_key=YOUR_KEY";`.

### **Functionality Overview**
The following APIs are used in this program:

* [CoinLayer](https://coinlayer.com/)
* [Fixer](https://fixer.io/)

CoinLayer is used to retrieve real-time quotes for the cryptocurrencies Bitcoin (BTC) and Ethereum (ETH) in United States Dollars (USD), while Fixer provides currency exchange rates from USD to Argentine Pesos (ARS) and Euros (EUR).

When the program starts, it makes a request to these APIs, which return information in JSON format. The necessary data is then extracted and stored in data structures.  
Next, we make a few calls to an assembly function, passing the cryptocurrency quote in USD and the conversion factor to the desired currency as parameters. This function performs the currency conversion and returns the result. In this way, we obtain the Bitcoin (BTC) and Ethereum (ETH) quotes in Argentine Pesos (ARS) and Euros (EUR).
