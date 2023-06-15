# Inseguitore solare

Autori: Daniele Ceribelli, Marco Aceti

## Descrizione

Il progetto consiste in una centralina di controllo per un inseguitore solare avanzato avente le seguenti funzionalità:
- __inseguire il Sole__: tramite l'ausilio di 4 fotoresistori, la centralina determina l'eventuale mossa dei motori per massimizzare l'efficienza dell'impianto fotovoltaico;
- __return-to-home automatico__: in caso di una situazione di scarsa luminosità (notte) o forte vento (rilevato mediante un anemometro analogico) la centralina posiziona il pannello solare in una posizione di sicurezza;
- __duplice modalità di funzionamento__: grazie all'uso del modulo display LED digitale TM1638, l'utente può selezionare due modalità distinte: _automatica_ (modalità predefinita) in cui la centralina agisce autonomamente o _manuale_ dove il movimento dei motori è determinato dalla pressione dei tasti sulla pulsantiera;
- __monitoraggio del funzionamento tramite MQTT__: la centralina &mdash; mediante la comunicazione tra i moduli Arduino Nano e ESP-01 &mdash; comunica a un server MQTT i valori dei sensori a fini di _quality-assurance_. 
Abbiamo infatti mostrato la possibilità di utilizzare applicazioni esterne come Prometheus e Grafana per creare visualizzazioni dei dati ricevuti consentendo una rapida rilevazione di eventuali problematiche garantendo un monitoraggio adeguato;
- __modello a loop chiuso__: per mezzo dell'utilizzo di due finecorsa e di un particolare circuito di retroazione, la centralina è in grado di pianificare le mosse successive anche in base allo stato reale del pannello.

## Lista materiali
- 1 x Arduino Nano
- 1 x ESP-01
- 4 x GL5538 fotoresistori
- 2 x motori DC
- 2 x 2 channel relay module
- 2 x finecorsa
- 1 x anemometro analogico
- 1 x TM1638
- 1 x logical level converter 5V - 3.3V
- 6 x resistenza 47 $\Omega$
- 2 x resistenza 10k $\Omega$
- 2 x AZDelivery breadboard power supply

## Schema elettrico

[![](./assets/schema_elettrico.png)](./assets/schema_elettrico.pdf)

## Architettura di rete

[![](./assets/architettura_rete.png)](./assets/architettura_rete.pdf)

## Risultati

![](./assets/progetto.jpg)

### Video dimostrativi

- [__Timelapse__](https://youtu.be/kQvNaYo899s)
- [__Rilevazione vento__](https://youtu.be/sqIIk6i1DkY)

### Dashboard Grafana

![](./assets/grafana.png)
