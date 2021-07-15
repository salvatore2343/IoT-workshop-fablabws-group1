
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
	* sudo apt update
	* sudo apt install -y mosquitto mosquitto-clients
	* sudo systemctl enable mosquitto.service
 * Testiamo digitando: mosquitto -v
 * scarichiamo e inseriamo le seguenti librerie all'interno di Arduino IDE
   	* https://github.com/marvinroger/async-mqtt-client/archive/master.zip
	* https://github.com/me-no-dev/AsyncTCP/archive/master.zip 
 * scriviamo il codice vero e proprio per connettere le due schede
 * il codice che abbiamo scritto aveva degli errori che abbiamo corretto 
 * ci connettiamo alla Raspberry attraverso PuTTY
 * Digitiamo:
	* bash <(curl -sL https://raw.githubusercontent.com/node-red/linux-installers/master/deb/update-nodejs-and-nodered)
	* sudo systemctl enable nodered.service
	* sudo reboot
 * riavviamo
 * digitiamo:
	* cd ~/.node-red
	* npm install node-red-dashboard
	* sudo reboot
 * riavviamo
 * digitiamo: node-red-start
 * apriamo una pagina google da un pc con la stessa rete alla quale è collegata la Raspberyy
   e scriviamo l'indirizzo IP della connessione e ":1880" e ci si apre il sito di ***NodeRed***
 * scriviamo nella barra di ricerca MQTT e mettiamo due blocchetti sul piano di lavoro
 * doppio click su uno e si apre una schermata 
	* cambiamo il server in: localhost 1883
 	* cambiamo topic inserendo il nome del canale della temperatura
  	* QoS:1
 * facciamo la stessa cosa con l'altro blocchetto con la differenza che questa volta inseriamo nel topic il canale dell'umidità
 * inseriamo due blocchetti gauge
 * doppio click su uno:
  	* nome: DHT
	* label: temperature
	* units: °C
	* range: 0-40
 * doppio click sul secondo:
	* nome: DHT
	* label: humidity
	* units: %
	* range: 0-100
 * colleghiamo i blocchetti e clicchiamo su deploy
 * andate all’indirizzo: http://raspberry-ip-address:1880/ui (ad esempio 192.168.1.250:1880/ui)
 * si apre una pagina dove possiamo vedere i valori di temperatura e umidità

# FINE