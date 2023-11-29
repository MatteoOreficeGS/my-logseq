tags:: #[[Models/Object Model/Object]]

- Deputato al #business-rule/calcolo-tariffario a partire dai dati di una fattura
- ## Problemi ricontrati #issue
	- il metodo checkReseller non dovrebbe decidere se utilizzare un client id ( invoiced o normale ) indicato sulla `$sped`, questo dovrebbe essere passato da fuori e fine #issue/design
		- la responsabilitá di scegliere quale client id utilizzare dovrebbe spettare al chiamate
		- le tariffe non hanno relazione alcuna con il concetto di #model/core/reseller
	- `calcolaSingoloNoloAddebito` non é chiaro se riceva sempre `$sped['corriere']` #issue/code/array-shape
	  ![image.png](../assets/image_1701177560694_0.png)
-
- # Metodi
	- ## `private function calcolaTariffa(...)`
		- Calcola il valore finale
		- Ritorna `false` in caso non ci siano le condizioni per calcolare la tariffa
		- ### Sequenza
			- fa alcuni controlli che potrebbero interrompere il calcolo della tariffa
				- ie: se il tipo listino non é conforme al listino per la quale la tariffa é specificata
			- controllo sulle zone incluse se `zone_incluse` diverso da `MONDO`
		- LATER proseguire a documentare
-
- ### #troubleshooting
	- ## Esaminare log chiamata FattureRate 
	  id:: 6553499b-9e4a-464c-b2f8-10d46d011e37
	  #[[model/fatturazione/FattureRateModel]]
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
		- Inoltre andrebbero #[[model/fatturazione/FattureRateModel]]