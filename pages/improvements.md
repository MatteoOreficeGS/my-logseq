filters:: {"issue" false}
alias:: idea

- # Definizione
- Un **improvement** rappresenta l'esigenza di aggiungere o cambiare il comportamento di un servizio, sistema, componente o processo #INFO
	- Non é una #issue
	- Richiede una fase di analisi e pianificazione e la soluzione di solito non é immediata
	- Non sempre interessa una parte esistente
- # Scopo
	- Pagina utilizzata per trovare i **backlink** a questo **tag**
- # Da fare
  :LOGBOOK:
  CLOCK: [2023-11-09 Thu 15:36:49]--[2023-11-09 Thu 15:36:50] =>  00:00:01
  CLOCK: [2023-11-09 Thu 15:36:50]--[2023-11-09 Thu 15:36:51] =>  00:00:01
  CLOCK: [2023-11-09 Thu 15:36:52]
  :END:
	- Realizzare una LogSeq/query per trovare tutti i blocchi che citano un miglioramento
		- sarebbe ottimo riuscire a esplodere i figli di ogni nodo taggato
		- in teoria una volta trovati i nodi taggati si dovrebbe poter fare una lista di tutti i sottonodi
- # Proposte di miglioramento generiche
	- Proposta X0
	  query-sort-by:: page
	  query-table:: true
	  query-sort-desc:: true
	  query-properties:: [:block :page]
	- Proposta X1
	- ....
	- Proposta XN
	- Proposta XN+1