tags:: #topic/import, #topic/export, #topic/courier-logic

- Per poter determinare se una spedizione é di tipo import sono necessarie queste condizioni :
	- la ISO country code del #model/core/cliente che bolletta la spedizione deve risultare uguale all'ISO country code del #model/core/destinatario della spedizione #topic/iso-country-code
	- la spedizione deve essere #topic/internazionale #business-rule/determinazione-ambito-internazionale
		- #action/ask-question #people/fabio-alessio é corretto dire cosi ? #question
			- questa decisione potrebbe essere diversa per corriere ?
	- quali altri dati potrebbero servire per determinare se una spedizione é di tipo import in generale ?
		- oltrepassare confini nazionali per questioni geografiche ?
	- `codice_cliente_dhl_expimp` é una funzione che solo per DHL sceglie quale contratto utilizzare per fatturazione o bollettazione, i contratti DHL sono salvati in #model/core/codici_cliente con una notazione separata da pipe `|`
-