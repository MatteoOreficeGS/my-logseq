- Rappresenta un #Model/Object deputato al #business-rules/calcolo-tariffario
- ## `calcolaTariffa(...)`
	-
	-
-
- # #troubleshooting
	- ## Esaminare log chiamata FattureRate 
	  id:: 6553499b-9e4a-464c-b2f8-10d46d011e37
	  #[[Progetti/Gsped API/Models/FattureRateModel]]
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
		- Inoltre andrebbero #[[Progetti/Gsped API/Models/FattureRateModel]]