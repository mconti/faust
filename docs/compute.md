Il metodo compute, è il cuore del calcolo DSP eseguito da faust.

La sua durata determina in qualche modo l'intera efficienza del sistema.

Sul mio ESP32 WROOM32 clockato a 240MHz, questo calcolo dura intorno a 90uS.

Vedi il test point 1 (+Width) in basso a sinistra

![Durata del metodo compute con 32 campioni](./images/DurataCompute vs Periodo 1.PNG)

La durata di questo calcolo dipende anche dal numero di campioni calcolati (buffer).
Nel caso precedende ad esempio questi campioni sono 32.

Se portiamo il numero di campioni a 16, la durata scende in proporzione e abbiamo una durata di 45uS

![Durata del metodo compute con 16 campioni](./images/DurataCompute vs Periodo 2.PNG)