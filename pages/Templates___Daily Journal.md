#### Daily Log templates
id:: 65771538-f0d1-490b-b3ab-65696d353761
template:: Daily Journal
template-including-parent:: false
type:: [[LS/Page/Journal]]
	- # Stand-Up Topics
		-
		- #### Target
		  heading:: 4
			- file
			- class
			- etc
		-
		-
	- # Attivitá
	  {{renderer :smartblock, resume-task, Resume Task ⏩️, false}} {{renderer :smartblock, new-task, New Task ➕, false}}
	- # Aiuto compilazione
	  collapsed:: true
	  Se hai bisogno di aiuto nelle compilazioni ecco alcuni riferimenti utili, questi blocchi sono inclusi con embed per evitare duplicazioni
		- {{embed ((6565c304-9cba-4238-91e6-36a5a4b45930))}}
		- {{embed ((6565c304-72f1-40e2-b2ac-a2eab69b4998))}}
		- {{embed ((6565c304-fbc2-4931-ab16-96384d8543be))}}
- #### Task shortcuts templates
	- ## Continuare un Task includendo il blocco ⏩️
	  template:: resume-task
	  template-including-parent:: false
	  id:: 65771538-7dd3-4f9b-a39b-6925aedef47c
		- ### Riprendo Task <%setInput: suffisso%> ⏩️
		  tags:: #event/task/resume
		  /e
	- ## Creare un nuovo Task
	  template:: new-task
	  template-including-parent:: false
	  id:: 65771538-9e0a-4c95-964c-5b60a4c80435
	  id:: 65771538-9e0a-4c95-964c-5b60a4c80435
	  id:: 65771538-9e0a-4c95-964c-5b60a4c80435
		- ### LATER <%setInput: intestazione_nuovo_task%>
		  tags:: event/task/begin, #topic/daily-journal-task
			- Descrivere il task qui
			- query-table:: true
			  collapsed:: true
			  #+BEGIN_QUERY
			  {:title "Task reference table ↗️ Click 🖱️to expand..." :query [:find (pull ?h [*])
			        :in $ ?parent
			        :where
			        [?parent :block/parent ?grandparent]
			        [?h :block/refs ?parent]
			  ]
			  :inputs [:parent-block]
			  :collapsed? true}
			  #+END_QUERY