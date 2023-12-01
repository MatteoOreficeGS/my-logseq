tags:: #topic/import, #topic/export

- Per poter determinare se una spedizione é di tipo import sono necessarie queste condizioni :
	- la spedizione deve essere #topic/internazionale #business-rule/determinazione-ambito-internazionale
	- la ISO country code del #model/core/cliente deve risultare uguale all'ISO country code del #model/core/destinatario della spedizione #topic/iso-country-code
		- #action/ask-question in questo caso il cliente
	-
-