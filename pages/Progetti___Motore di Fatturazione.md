# #issue
	- gli utenti in primis sbagliano il formato del file #UX #[[Progetti/Gsped Legacy]]
	- RigaFattura contiene del codice specifico per GLS che tratta `p_tax` eche non dovrebbe stare li, in qualche ramo avevo predisposto una fix per generalizzare `getRateRequest` in maniera che fosse interamente **overridable** ma forse non é stata mergiata per interruzione del lavoro #OOP/Design #issue/code
		- ~~ho giá creato una #jira/issue [FT-36|specializzare opener GlsRigaFattura per trattare p_tax nella classe figlia (Refactoring)](https://gsped.atlassian.net/browse/FT-36)~~
- # #improvements
	- creare un tool da riga di comando per fare analisi del log con semplici parametri, non sarebbe male usare un binario GO oppure uno shell script ancore meglio
- # #troubleshooting
  :LOGBOOK:
  CLOCK: [2023-11-09 Thu 09:02:28]--[2023-11-09 Thu 09:02:28] =>  00:00:00
  :END:
	- ## Elencare tutti i client id per cui non esiste una tariffa
		- ```shell
		  grep 'Risposta.*Rate.*15386' /tmp/CtrFatGsped.log | \
		  	grep -oP 'Nessuna tariffa trovata per cliente \d+' | \
		  	sort -h | uniq
		  ```
	- ## Mostrare risposte #Domain/Model/FattureRate  dal log `CtrFatt.log`
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
	- ## Esaminare log chiamata #Domain/Model/FattureRate
		- Per poter esaminare il log dobbiamo usare la macchina di staging
		- effettuare una chiamata come la seguente
		- ```
		  GET http://apistaging.aws.gsped.it/stampasi/FattureRate/?
		      client_id=7&
		      colli=3&
		      corriere=101&
		      date_created=2023-10-02&
		      peso=35.60&
		      rcpt_cap=20900&
		      rcpt_city=monza&
		      rcpt_country_code=IT&
		      sender_cap=20124&
		      sender_city=Milano&
		      sender_country_code=IT&
		      servizio=0&
		      volume=18&
		      documenti=0&
		      valore=0.000&
		      tipo_listino=passivo&
		      fuel=0&
		      fuel_int=0&
		      fuel_air=0
		  ```
		- Quindi esaminare il log
		- ```bash
		  docker exec  api cat '/tmp/api-2023-10-11.txt' | less
		  ```
		- Conviene creare documentazione di alto livello per i componenti di GSped, ad esempio il modello #[[Instrument/C4]] puó essere usato per descrivere ad alto livello un sistema
		- #Domain/Model/FattureRate