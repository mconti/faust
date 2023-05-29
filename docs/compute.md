Il metodo compute, è il cuore del calcolo DSP eseguito da faust.

La sua durata determina in qualche modo l'intera efficienza del sistema.

Sul mio ESP32 WROOM32 clockato a 240MHz, questo calcolo dura intorno a 90uS.

Vedi il test point 1 (+Width) in basso a destra

![Durata del metodo compute](./images/DurataCompute vs Periodo 1.PNG)

![Durata del metodo compute](./images/DurataCompute vs Periodo 2.PNG)