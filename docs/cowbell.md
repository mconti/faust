```faust
declare name 		"mauriCowBell";
declare version 	"1.0";
declare author 		"Maurizio";
declare license 	"BSD";
declare copyright 	"(c)Fablab Romagna 2023";


//-----------------------------------------------
// 			TR-808 CowBell
//-----------------------------------------------

import("stdfaust.lib");

// Pulsante
trigger = button("Cow");

// slider per regolare bene la durata
durata = hslider("delay [unit:s]", 0.4, 0.001, 0.5, 0.01);

// crea il "colpo" con spegnimento esponenziale (senza la 'e' diventa una rampa, cambia molto)
inviluppo = en.adsre( 0, durata, 0, durata, trigger );

// le due frequenze base
o800 = os.square(800) * inviluppo;
o540 = os.square(540) * inviluppo;

// il filtro passa banda in uscita
bandPass = fi.bandpass( 1, 750, 850);

// Mettiamo tutto assieme
process = vgroup(
    "TR-808 CowBell", 
    o800 + o540 : bandPass
)

```