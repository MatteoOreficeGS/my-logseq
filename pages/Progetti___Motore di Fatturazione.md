# Problemi noti
tags:: #issue
	- gli utenti in primis sbagliano il formato del file #topic/UX #[[Progetti/Gsped Legacy]]
	- RigaFattura contiene del codice specifico per GLS che tratta `p_tax` eche non dovrebbe stare li, in qualche ramo avevo predisposto una fix per generalizzare `getRateRequest` in maniera che fosse interamente **overridable** ma forse non é stata mergiata per interruzione del lavoro #issue/code #Process/SDC/design/OOP
		- ~~ho giá creato una #jira/issue [FT-36|specializzare opener GlsRigaFattura per trattare p_tax nella classe figlia (Refactoring)](https://gsped.atlassian.net/browse/FT-36)~~
- # Miglioramenti
  tags:: #improvements, #issue/feature/internal, #issue/tools
	- creare un tool da riga di comando per fare analisi del log con semplici parametri, non sarebbe male usare un binario GO oppure uno shell script ancore meglio
- # Risoluzione problemi comuni
  tags:: #troubleshooting
  :LOGBOOK:
  CLOCK: [2023-11-09 Thu 09:02:28]--[2023-11-09 Thu 09:02:28] =>  00:00:00
  :END:
	- ## Elencare tutti i client id per cui non esiste una tariffa
		- ```shell
		  grep 'Risposta.*Rate.*15386' /tmp/CtrFatGsped.log | \
		  	grep -oP 'Nessuna tariffa trovata per cliente \d+' | \
		  	sort -h | uniq
		  ```
	- ## Mostrare risposte #[[model/fatturazione/FattureRateModel]]  dal log `CtrFatt.log`
		- ```shell
		  zgrep 'Risposta.*Rate.*15393' /tmp/CtrFatGsped.log | \
		  	grep -oP 'Rate response":"\K.*' | sort -h | uniq
		  ```
	- ## Estrarre dal log `CtrFatt.log` solo un'elaborazione
		- ```shell
		  zcat /tmp/CtrFatGsped.log | \
		  	sed -ne  '/Inizio elaborazione.*15829/,/Tempo di elaborazione.*"15829"/p' \
		      > 15829.txt
		  ```
- # Riferimenti utili
	- [Dizionario dati del motore di fatturazione](https://docs.google.com/spreadsheets/d/1wdo_0-dpdy3BL9HnUQAManeSG5NExVXqzynDyqBSkW4/edit?pli=1#gid=0) su google spreadsheet, utile per nuove mappature e documentare campi consentiti
	- [Censimento di tutti gli opener per unificazione](https://docs.google.com/spreadsheets/d/1bvUE3HTSPNIgVh0FO4kRRrFdZMW8cQjr/edit?pli=1#gid=877752362) su google spreadsheet
	-
	-