tags:: #topic/import, #topic/export

- Per poter determinare se una spedizione é di tipo import sono necessarie queste condizioni :
	- la spedizione deve essere #topic/internazionale #business-rule/determinazione-ambito-internazionale
	- la ISO country code del #model/core/cliente che bolletta la spedizione deve risultare uguale all'ISO country code del #model/core/destinatario della spedizione #topic/iso-country-code
		- #action/ask-question #people/fabio-alessio é corretto dire cosi ?
	- questa decisione potrebbe essere diversa per corriere ?
	- quali altri dati potrebbero servire per determinare se una spedizione é di tipo import ?
	- `codice_cliente_dhl_expimp` é una funzione che solo per DHL sceglie quale contratto utilizzare per fatturazione o bollettazione, i contratti DHL sono salvati in
-