- root node
  template:: Daily Journal
  template-including-parent:: false
	- # Attivitá
		- ### Testo descrittivo attivitá 1
		  client:: fill
		  courier:: fill
		  requester:: fill
		  channel:: fill
			- attivitá log statement 1
			- attivitá log statement 2
			- attivitá log statement ...
			- attivitá log statement N
	- ## Help compilazione
	  #INFO
		- ## Attivitá
		- ### Intestazione attivitá
			- **descrive l'attivitá da svolgere** iniziando con un **verbo**, che implica lo svolgimento di una certa azione,
			- alla fine utilizzare dei tag per indicare
				- la sorgente della richiesta, mail, slack etc
				  logseq.order-list-type:: number
				- richiedente, cliente ed eventualmente il corriere
				  logseq.order-list-type:: number
		- ### Sotto blocchi
			- oggetto della richiesta come il nome del progetto o della codebase
			- link ad una #jira/issue
			- la sequenzialitá indica cosa fatto prima o dopo
			- valutare uso di block properties
	- ## Riferimenti utili
		- Vai alla guida del processo [[Process/GTD/MyDailyPlanning]] per vederlo o modificarlo
		- Vai al template del [[Templates/Daily Journal]] per vederlo o modificarlo