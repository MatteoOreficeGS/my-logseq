# Problemi rilevati
	- gli utenti in primis sbagliano il formato del file #UX
	- RigaFattura contiene del codice specifico per GLS che tratta `p_tax` eche non dovrebbe stare li, in qualche ramo avevo predisposto una fix per generalizzare `getRateRequest` in maniera che fosse interamente **overridable** ma forse non é stata mergiata per interruzione del lavoro
- # Idee di miglioramento
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
	- ## Mostrare tutte le risposte di un'elaborazione
		- ```shell
		  zgrep 'Risposta.*Rate.*15393' /tmp/CtrFatGsped.log | \
		  	grep -oP 'Rate response":"\K.*' | sort -h | uniq
		  ```