# Da analizzare e definire
	- Usare anche delle block properties
	- Ragionare su **proprietá** comuni a tutti i **templates** e **tags**
		- urgenza sicuramente é un parametro comune
		- target codebase ?
		- cliente che ha richiesto
		- corrieri interessati
		- Jira al momento ha troppi #jira/issue/type eterogenei  andrebbero uniformati, a cascata crea diversi problemi tra cui:
			- cui assenza di informazioni specifiche e richieste sui tasks
			- difficoltá nelle queries e filtri
			- TODO eventualmente creare un modello system wide per un tipo di #jira/issue dedicato #jira/admin-request #improvements/jira
	- Tipi di richiesta per la sezione del Daily Journal ((654bdedb-e744-4de0-91db-e137747446b7))
	- Tipi di task da svolgere per il #Processi/GTD
		- Considerazioni
			- Ragionare su proprietá comuni a tutti i **tasks**
			  id:: 654d0c7c-b44b-4a3c-b69e-fb443eee047e
			- Un grande problema é il modo con cui viene descritto un task da fare, é assolutamente necessario definire un #Templates per i vari task che mi forzi a fare certe operazioni #[[Process/GTD/MyDailyPlanning]]
			  id:: 654d06e4-98c0-44f7-81e9-5a999d3bea1d
			  :LOGBOOK:
			  CLOCK: [2023-11-09 Thu 19:10:16]
			  :END:
			- NOW Classificare per un certo periodo di tempo i tipi di task che si presentano guardando il **Daily Journal**
			  SCHEDULED: <2023-12-31 Sun>
			  :LOGBOOK:
			  CLOCK: [2023-11-09 Thu 19:38:00]
			  :END:
		- **Meeting Task**
			- contemplare le azioni finali del  meeting
			- leggere qualche articolo su come tenere un meeting
			- LATER fare un #Process/Sharing/Howtos su come tenere un meeting
		- **Bugfixes Task** #bug/fix
			- creare un template con delle props in maniera da censire subito il bug
			- a seconda del bug che si crea potrebbe essere diversa la sequenza di code da fare
		- **Pull Request Review Task** #PR/review
			- si intende una richiesta per revisionare una PR
		- **Suppor Request Task** #[[Process/SDC/support]]
			- Tipo #hotfix/database request task o in generale #Process/SDC/database-migrations
			  id:: 654d1ffa-e50c-4141-aadf-7a8373f3eee2
				- analizza target potenziale della modifica
				  logseq.order-list-type:: number
				- crea e test codice sql
				  logseq.order-list-type:: number
				- inserisci il codice in una card jira 
				  logseq.order-list-type:: number
				- assegnati e metti in progress
				  logseq.order-list-type:: number
	- Template per tag pages
		- Classiche tag page, di solito contiene una spiegazione dello scopo della pagina
	- Template per il #Troubleshooting
		- Al fine di circoscrivere il formato di domanda e risposta
		- dettagli di codice
		- azioni manuali da intraprendere
	- Template per una #issue
	- Template per un #improvements
		- Non deve sostituire l'analisi che sfocierá in una card JIRA
		  background-color:: red
		- Indicare un livello di desiderata NICE TO HAVE, MUST HAVE, etc
	- Template elenco di domande e risposte
		- da usari in altri template ?
- # Tags e properties
	- Ragionare anche su quali metadati utilizzare per ritrovare questo contenuto che viene creato sin da subito
	- LATER Ricordare che é disponibile  ereditarietá e fare dei test su di #LogSeq https://discuss.logseq.com/t/tagging-every-block-or-using-block-properties/11612