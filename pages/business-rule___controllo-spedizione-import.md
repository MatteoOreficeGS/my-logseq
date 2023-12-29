tags:: topic/import-export, #topic/courier-logic

- Per poter determinare se una spedizione é di tipo import sono necessarie queste condizioni :
	- la ISO country code del #model/core/cliente che bolletta la spedizione deve risultare uguale all'ISO country code del #model/core/destinatario della spedizione #topic/iso-country-code
	- la spedizione deve essere #topic/internazionale #business-rule/determinazione-ambito-internazionale
		- #action/ask-question #people/fabio-alessio é corretto dire cosi ? #question
			- questa decisione potrebbe essere diversa per corriere ?
	- quali altri dati potrebbero servire per determinare se una spedizione é di tipo import in generale ?
		- oltrepassare confini nazionali per questioni geografiche ?
	- ### DHL
	  tags:: #topic/courier-logic, #model/core/DHLSoapModel, #model/core/DHLModel 
	  Per DHL il cliente indica codici contratto multipli, esistono poi delle funzioni che determinano il codice contratto da utilizzarsi in diverse condizioni, i contratti DHL sono salvati in #model/core/codici_cliente con una notazione separata da pipe `|`, alcuni riferimenti nel codice
		- `\App\models\DHLSoapModel::codice_cliente_dhl_expimp`
		- `\App\models\FattureRateModel::checkSpedImport`
		- `\App\models\DHLModel::codiceClienteExpImp`
-