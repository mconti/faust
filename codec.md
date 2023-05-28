## Il codec
Il mio obiettivo è quello di creare un oggetto a se stante, governato da un microcontroller economico, che generi suoni progettati con l'IDE di faust.

Faust genera codice C++ per molte piattaforme tra cui [Teensy](https://faustdoc.grame.fr/tutorials/teensy/) e [ESP32](https://faustdoc.grame.fr/tutorials/esp32/).

Per farlo, crea una serie di classi contenute in un solo file.cpp.

Per funzionare su un embedded serve naturalmente n CoDec; un dispositivo hardware che contiene sia un ADC per l'acquisizione del segnale analogico, sia un DAC per la generazione del suono in uscita.

Negli esempi forniti al 28 maggio 2023, si fa riferimento a due tipi di Codec: 
- il WM

[La scheda ESP32 Audio-Kit di Seeed Studio](https://www.mouser.it/ProductDetail/713-107990093)
 può essere acquista da mouser ma io non ci sono riuscito.


 Mouser mi ha risposto che l'ordine non poteva essere evaso:

Greetings,

Thank you for returning the form.

Unfortunately, the item on your purchase order has export restrictions imposed by the US Government and we are unable to ship this item to you. 

The CCATS and 740 license information that allows us to export out of the U.S. is unavailable at this time.  

We are unable to ship these item(s) to you and they have been removed from your order. 

We apologize for any inconvenience this may have caused.

Part Number                                      Quantity

713-107990093                                  2


If you would like us to assist in finding a substitute or to ship the remainder of your order, please contact your local customer service team for assistance.

Best Regards,

Export Compliance Team

export@mouser.com

www.mouser.com

