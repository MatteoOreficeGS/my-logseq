filters:: {"done" false}

- # Definizione
  Il calcolo tariffarrio é il processo attraverso il quale viene determinato il prezzo di una spedizione
- # Attuale implementazione
	- ## Data Model
		- Nel nostro [[Models/Data Model]] troviamo le seguenti #[[Models/Data Model/Entity]]
			- [[model/fatturazione/tariffe]]
			- [[model/fatturazione/tariffe_fasce]]
			- [[model/fatturazione/tariffe_clienti]]
	- ## Selezione tariffa e fascia
	  tags:: #topic/fascia, #model/fatturazione/tariffe_fasce, #model/fatturazione/tariffe
		- Prima del calcolo vero e proprio viene determinata in sequenza la tariffa e poi la fascia prescelta.
		- [[draws/2023-11-15-15-30-57.excalidraw]]
		  #Instrument/DFD che fornisce una semplice rappresentazione del processo di calcolo tariffario
	- ## Calcolo costo spedizione
-
- ## Riferimenti
	- ### GitBook
		- https://app.gitbook.com/o/-LhpbdRCZplUyqAg775u/home?q=calcolo+tariffario