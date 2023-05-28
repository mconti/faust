## Il codec
Il mio obiettivo è quello di creare un oggetto a se stante, governato da un microcontroller economico, che generi suoni progettati con l'IDE di faust.

Faust genera codice C++ per molte piattaforme tra cui [Teensy](https://faustdoc.grame.fr/tutorials/teensy/) e [ESP32](https://faustdoc.grame.fr/tutorials/esp32/).

Per farlo, crea una serie di classi contenute in un solo file.cpp.

## Il codec

Per far girare il codice faust su un dispositivo embedded, serve naturalmente un Codec; un componente hardware che contiene sia un ADC (COdificatore) per l'acquisizione del segnale analogico, sia un DAC (DECodificatore) per la generazione del suono in uscita.

## le schede consigliate

Negli esempi forniti (ad oggi, 28 maggio 2023), per quanto riguarda ESP32, si fa riferimento a due tipi di Codec montati su due schede ESP32 distinte: 
- [La scheda TTGO-TAudio di LiLyGo](https://it.aliexpress.com/item/32846510254.html?gatewayAdapt=glo2ita) non più disponibile.
- [La scheda ESP32 Audio-Kit di Seeed Studio](https://www.mouser.it/ProductDetail/713-107990093) dal costo di 17 Euro + spese ma che mouser non esporta in Italia, o almeno,quando ci ho provato io, ho ricevuto questa comunicazione:

*Greetings,

Unfortunately, the item on your purchase order has export restrictions imposed by the US Government and we are unable to ship this item to you. 

The CCATS and 740 license information that allows us to export out of the U.S. is unavailable at this time.  

We are unable to ship these item(s) to you and they have been removed from your order. 

We apologize for any inconvenience this may have caused.
*

| Part Number   | Quantity |
|:--------------|:---------|
| 713-107990093 | 2        |

*
If you would like us to assist in finding a substitute or to ship the remainder of your order, please contact your local customer service team for assistance.

Best Regards,

Export Compliance Team

export@mouser.com

www.mouser.com
*

## Il chip WM8978
Entrambe le schede utilizzano il componente [Wolfson WM8978](https://www.mouser.com/datasheet/2/76/WM8978_v4.5-1141768.pdf) che la ditta produttrice [Cirrus Logic](https://www.mouser.it/ProductDetail/Cirrus-Logic/WM8978CGEFL-V?qs=G8wrXCBxhFvEsBnvQH22jg%3D%3D) ha messo fuori produzione.

Sul sito mouser ne esistono ad oggi ancora [3000 pezzi](https://www.mouser.it/ProductDetail/Cirrus-Logic/WM8978CGEFL-V?qs=G8wrXCBxhFvEsBnvQH22jg%3D%3D) ma non so se poi me li spediscono e comunque è un fine vita, non conviene.

Come sostituto, la Cirrus Logic consiglia questo [WM8962](https://www.mouser.it/datasheet/2/76/WM8962B_v4_2-1142164.pdf) ma non ho idea di quanto sia compatibile a livello software.

Il codec infatti ha due canali di comunicazione con l'esterno: 
- una porta I2C per la configurazione dei registri interni
- e una porta I2S per l'I/O del flusso audio.

e il driver creato da faust non è detto che lo governi correttamente. Andrebbe perlomeno fatto un upgrade di questo driver.




