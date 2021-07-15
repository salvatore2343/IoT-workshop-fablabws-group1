
# Internet Of Things

 2 schede: Raspberry Pi Zero W,Esp32;

 * configuriamo ***raspberry-SSD*** seguendo le slide del pdf (workshop)
 * configuriamo ***raspberry-VNC*** seguendo le slide del pdf (workshop)
 * per la configurazione raspberry-VNC abbiamo bisogno di scaricare ***PuTTY*** 
   seguendo le slide del pdf (workshop)
 * scarichiamo ***Aruino IDE*** seguendo le slide del pdf (workshop)
 * per testare il funzionamento della scheda Esp 32 carichiamo su Arduino IDE 
   un primo codice molto semplice
 * per testare il funzionamento del sensore di umidità carichiamo du Arduino IDE
   un altro codice
 * proseguiamo con il montaggio del circuito utilizzando un sensore di umidità
 * abbiamo avuto dei problemi in quanto dava un errore di lettura dei sensori
 * dopo svariati tentativi siamo riusciti a risolvere l'errore
 * stiamo cercando di cennettere le due schede ma stiamo avendo molti problemi 
   durante i diversi passaggi e stiamo cercando di risolverli cambiando rete 
   alla quale è connessa la Raspberry. 
 * siamo riusciti così a connetterci alla Raspberry attraverso ***PuTTY***
 * Digitiamo:
	a. sudo apt update
	b. sudo apt install -y mosquitto mosquitto-clients
	c. sudo systemctl enable mosquitto.service
 * Testiamo digitando: mosquitto -v
 * scarichiamo e inseriamo le seguenti librerie all'interno di Arduino IDE
   	1° https://github.com/marvinroger/async-mqtt-client/archive/master.zip
	2° https://github.com/me-no-dev/AsyncTCP/archive/master.zip 
 * scriviamo il codice vero e proprio per connettere le due schede
 * il codice che abbiamo scritto aveva degli errori che abbiamo corretto 
 *