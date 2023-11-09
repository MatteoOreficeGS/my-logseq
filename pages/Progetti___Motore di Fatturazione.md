# Problemi rilevati #backlog
	- gli utenti in primis sbagliano il formato del file #UX #[[Progetti/Gsped Legacy]]
	- RigaFattura contiene del codice specifico per GLS che tratta `p_tax` eche non dovrebbe stare li, in qualche ramo avevo predisposto una fix per generalizzare `getRateRequest` in maniera che fosse interamente **overridable** ma forse non é stata mergiata per interruzione del lavoro #OOP/Design
- # Idee di miglioramento #improvements
	- creare un tool da riga di comando per fare analisi del log con semplici parametri, non sarebbe male usare un binario GO oppure uno shell script ancore meglio
- # DONE #Troubleshooting
  :LOGBOOK:
  CLOCK: [2023-11-09 Thu 09:02:28]--[2023-11-09 Thu 09:02:28] =>  00:00:00
  :END:
	- ## Elencare tutti i client id per cui non esiste una tariffa
		- ```shell
		  grep 'Risposta.*Rate.*15386' /tmp/CtrFatGsped.log | \
		  	grep -oP 'Nessuna tariffa trovata per cliente \d+' | \
		  	sort -h | uniq
		  ```
	- ## Mostrare le risposte di [[Domain/FattureRate]] di un'elaborazione
		- ```shell
		  zgrep 'Risposta.*Rate.*15393' /tmp/CtrFatGsped.log | \
		  	grep -oP 'Rate response":"\K.*' | sort -h | uniq
		  ```
	- ## Estrarre dal log CtrFatt.log solo un'elaborazione
		- ```shell
		  grep 'Risposta.*Rate.*15386' /tmp/CtrFatGsped.log | \
		  	grep -oP 'Nessuna tariffa trovata per cliente \d+' | \
		  	sort -h | uniq
		  ```
-