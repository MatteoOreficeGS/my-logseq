# Daily Log Template
template:: Daily Journal
template-including-parent:: false
type:: [[LS/Page/Journal]]
collapsed:: true
	- # Stand-Up Topics
		- topic 1
		- topic 1
		- topic 3
	- # Attivitá
	  {{renderer :smartblock, resume-task, Resume Task ⏩️, false}} {{renderer :smartblock, new-task, New Task ➕, false}}
	- # Aiuto compilazione
	  Se hai bisogno di aiuto nelle compilazioni ecco alcuni riferimenti utili, questi blocchi sono inclusi con embed per evitare duplicazioni
		- {{embed ((6565c304-9cba-4238-91e6-36a5a4b45930))}}
		- {{embed ((6565c304-72f1-40e2-b2ac-a2eab69b4998))}}
		- {{embed ((6565c304-fbc2-4931-ab16-96384d8543be))}}
- # Task shortcuts
	- ## Continuare un Task includendo il blocco ⏩️
	  template:: resume-task
	  template-including-parent:: false
		- ### Riprendo Task <%setInput: suffisso%> ⏩️
		  tags:: #resume-task 
		  /
	- ## Creare un nuovo Task
	  template:: new-task
	  template-including-parent:: false
		- ### <%setInput: intestazione_nuovo_task%>
		  tags:: topic, topic, topic
			- TODO Descrizione task
-