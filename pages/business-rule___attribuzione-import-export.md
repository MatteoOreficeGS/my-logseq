tags:: topic/import-export, #topic/courier-logic, #issue/need-for-analysis

- Per poter determinare se una spedizione é di tipo import sono necessarie queste condizioni :
	- la ISO #models/gsped/core/clienti/country del #models/gsped/core/clienti che bolletta la spedizione deve risultare uguale all'#topic/iso-country-code  del #models/gsped/core/destinatario della spedizione
	- la spedizione deve essere #topic/internazionale, vedi anche #business-rule/attribuzione-ambito-internazionale
	- quali altri dati potrebbero servire per determinare se una spedizione é di tipo import in generale ?
		- oltrepassare confini nazionali per questioni geografiche seppure la spedizione rimanga #topic/nazionale
	- ### DHL
	  tags:: #topic/courier-logic, #models/gsped/core/DHLSoapModel, #models/gsped/core/DHLModel, #models/gsped/core/codici_cliente
		- Per DHL il cliente puó inserire in #gsped #topic/codici-contratto multipli per i vari ambiti della spedizione, es: #topic/camionistico
		- Esistono delle funzioni che determinano il #topic/codice-contratto **corretto** da utilizzarsi nelle diverse condizioni, es: spedizione internazionale di #topic/import
		- I contratti DHL sono salvati in #models/gsped/core/codici_cliente con una notazione separata da pipe `|`, qui di seguito alcuni riferimenti nel codice che trattano il formato in questione
		  tags:: #topic/conventions
		  ```
		  \App\models\DHLSoapgsped::codice_cliente_dhl_expimp
		  \App\models\FattureRategsped::checkSpedImport
		  # alla data 2023-12-29 questo metodo non usa il client_id ma definisce import in maniera statica
		  # in base al fatto che la country del destinatario sia 'IT'
		  \App\models\DHLgsped::codiceClienteExpImp
		  ```