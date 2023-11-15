- Descrive il processo da me adottato per la pianificazione giornaliera
- # NOTA BENE #WARNING
	- Questo processo serve per fare completare le tue attivitá giornaliere basandoti sempre sui task presenti in #jira quindi é essenziale che qualsiasi attivitá che richieda piú di 10 minuti per essere eseguita venga censita in #jira
	- Per aiutarti ad eseguire il processo il tuo Today Journal viene inizializzato ogni giorno con il template [[Templates/Daily Journal]] che fornisce una struttura di base pensata per i passi da eseguirsi in questo processo
- # Pianificazione ⏰
	- Annota le richieste per nuove attivitá da svolgere nel **Today Journal**
	  logseq.order-list-type:: number
		- Puoi salvare nel blocco  del Journal tutte queste informazioni suddivise per provenienza
		  logseq.order-list-type:: number
	- Valuta #jira/issue/effprt delle card per inserimento in #jira
	  logseq.order-list-type:: number
		- Converti le attivitá che richiedono piú di 10 minuti in #issue/jira , puoi marcare con questo tag la necessitá di crearne una #jira/issue/comeout
		  logseq.order-list-type:: number
		- Le attivitá veloci non vanno trasferite in #jira
		  logseq.order-list-type:: number
			- Pensare ad un modo per marcare queste attivitá di veloce svolgimento nel Journal #improvements/logseq, scegli un tag per esempio #jira/untracked
			  logseq.order-list-type:: number
		- Per le attivitá di sviluppo **devi sempre creare** le card nella board [Analisi](https://gsped.atlassian.net/jira/software/projects/AN/boards/37) , queste non possono andare subito in lavorazione ma vanno pianificate con il team
		  logseq.order-list-type:: number
			- Serve un #Templates per le attivitá di **analisi**
			  logseq.order-list-type:: number
	- Identifica le #jira/issue con alta prioritá
	  logseq.order-list-type:: number
		- se sono troppe usa il plugin per export di Jira e condividi con il tuo capo
		  logseq.order-list-type:: number
		- se hai dubbi sulle prioritá usa il plugin per export di Jira e condividi con il tuo capo
		  logseq.order-list-type:: number
		- ci possono essere anche task nello stato **NOW** dal giorno precedente che non sono stati terminati o dimenticati, hai due scelte
		  logseq.order-list-type:: number
			- se non sono #jira/untracked chiuderli con un commento
				- > in linea di massima questi task devono esistere in #jira quindi é inutile tenerli aperti
			- diversamente se li trovi aperti il giorno successivo e sono #jira/untracked meglio farli diventare delle #jira/issue perché se scavallano il giorno non sono attivitá rapide e meritano di essere censite in #jira
	- Scegli a questo punto le attivitá **da fare oggi** dall'elenco dalla cima delle attivitá master ordinaté per prioritá decrescente in #jira e creale nella TodoList del #[[Templates/Daily Journal]] con stato **NOW**
	  logseq.order-list-type:: number
	  > in questo modo restano visibili come i task su cui stai lavorando e li vedrai anche il giorno successivo per continuarli
	- Valutare i task con la **scadenza** in Jira
	  logseq.order-list-type:: number
	- Lavora sulle cose che hai da fare
	  logseq.order-list-type:: number
		- puoi marcare le attivitá con NOW per ricordare meglio costa stai facendo
		  logseq.order-list-type:: number
	- Durante l'attivitá o al suo termine
	  logseq.order-list-type:: number
		- ricordati di **annotare sempre** le card #jira in maniera che tutti leggano l'avanzamento delle attivitá
		  logseq.order-list-type:: number
		- ricorda di non inserire in #LogSeq informazioni che devono essere condivise in #jira #Process/Sharing
		  logseq.order-list-type:: number
		- in #LogSeq puoi ad esempio inserire
		  logseq.order-list-type:: number
			- informazioni o riflessioni private che andrebbero perse
			  logseq.order-list-type:: number
			- tutto ció che aiuti ad estendere la rete di conoscenze di questa **knowledge base**
			  logseq.order-list-type:: number
		- aggiornare anche questa stessa pagina per meglio descrivere cosa  **debba** o **non debba** essere assolutamente scritto in #LogSeq
		  logseq.order-list-type:: number
	- a fine giornata
	  logseq.order-list-type:: number
		- marca come fatte le cose completate
		  logseq.order-list-type:: number
- # Interruzioni
	- Da completare il meccanismo con cui vengono censite le interruzioni, che sono a volte devastanti
- # Generazione indiretta di task
  Attivitá da tenere a mente durante il giorno
	- rilevamento di #issue/code durante esplorazione del codice
	- rilevamento di #improvements/ineffectiveness nei processi
- # Considerazioni
	- le **attivitá per un certo cliente da lui richieste** vanno taggare in qualche maniera altrimenti potrei perderle di vista #jira/issue, intendo dire che non sempre nelle #jira/issue viene indicato chiaramente se é stata una richiesta del cliente a farla aprire #improvements/ineffectiveness #[[Process/Customer Satisfaction]] #jira/issue/type #issue/process
		- questo é un problema se ha fretta e non viene usata una data di scadenza poiché la richiesta va in concorrenza ad altre non espressamente richieste
		- saperlo aiuta anche nel sceglierle come prioritarie in caso di numerose richieste
		- diverso se sono per un cliente ma non sono richieste direttamente da lui, potrebbero non essere cosí urgenti
	- Altra questione fondamentale é l'**attribuzione di una prioritá** ad una attivitá, ad oggi é molto difficile, si potrebbe calcolare uno score basandosi su una serie di parametri in una tabella #[[Process/SDC/issue-tracking/risk-assesment]] #issue/process #REMEDY
	- quali attivitá che richiedono #Process/SDC/analysis devono finire nella board dell'Analisi?  Anche qui é fondamentale la #[[Process/SDC/issue-tracking/risk-assesment]] e ad oggi é un problema #issue/process  #question/ask ?
		- esiste una soglia di effort minima ?
		  id:: 6551eae3-8770-4e22-86d8-c6e784a349c2
	- Un altro problema grave oggi é non avere la data di scadenza per i task in Jira, talvolta non é nemmeno possibile settarla ! #issue/jira #issue/process #[[Process/Customer Satisfaction]] #Process/GTD #[[Process/SDC/issue-tracking/risk-assesment]] #REMEDY