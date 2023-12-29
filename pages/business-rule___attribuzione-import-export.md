tags:: topic/import-export, #topic/courier-logic

- Per poter determinare se una spedizione é di tipo import sono necessarie queste condizioni :
	- la ISO country code del #model/core/cliente che bolletta la spedizione deve risultare uguale all'#topic/iso-country-code  del #model/core/destinatario della spedizione
	- la spedizione deve essere #topic/internazionale, vedi anche #business-rule/determinazione-ambito-internazionale
	- quali altri dati potrebbero servire per determinare se una spedizione é di tipo import in generale ?
		- oltrepassare confini nazionali per questioni geografiche seppure la spedizione rimanga #topic/nazionale
	- ### DHL
	  tags:: #topic/courier-logic, #model/core/DHLSoapModel, #model/core/DHLModel, #model/core/codici_cliente
		- Per DHL il cliente puó inserire in #gsped #topic/codici-contratto multipli per i vari ambiti della spedizione, es: #topic/camionistico
		- Esistono delle funzioni che determinano il #topic/codice-contratto **corretto** da utilizzarsi nelle diverse condizioni, es: spedizione internazionale di #topic/import
		- I contratti DHL sono salvati in #model/core/codici_cliente con una notazione separata da pipe `|`, alcuni riferimenti nel codice
		  tags:: #topic/conventions
			- `\App\models\DHLSoapModel::codice_cliente_dhl_expimp`
			- `\App\models\FattureRateModel::checkSpedImport`
			- `\App\models\DHLModel::codiceClienteExpImp`