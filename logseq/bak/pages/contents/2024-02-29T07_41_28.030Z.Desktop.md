-
- # Journal
- Il journal viene creato a partire da #[[Templates/Daily Journal]]
	- Tutte le pagine con il tag #[[Templates/Daily Journal/Tags]] possono essere utilizzare come tag nel journal
	- Alcune parti del #[[Templates/Daily Journal]] vendono embeddate per evitare ripetizioni #[[Templates/Daily Journal/Embeds]]
- # Long term success 🎯
  Obiettivi a lungo termine a cui mirare
	- ## Miglioramento processi
	  Esplora la sezione che documenta #[[Process/Process Managament/Improvement]]
- # Meeting recenti 🧑‍🤝‍🧑
	- {{query (and [[meeting]] (not (page [[Process/Collaboration/Meeting]])) (not (page [[Templates]])) (not (page [[meeting]])))}}
	  query-table:: true
	  query-properties:: [:block :page]
	  query-sort-by:: page
	  query-sort-desc:: true
- # Organizzazione grafo
	- Vedere #[[Architettura Grafo]] per architettura di questo grafo
- # Templates
	- Vedere #Templates per i vari tempates disponibili
- # Guide d'uso
	- Tag correlati alle guide sono: #doc/howtos e #doc
	  {{query (or (page-tags [[doc/howtos]]) (page-tags [[doc/team]]) (page-tags [[process/knowledge sharing]]))}}
	- Guide alla comprensione dei concetti fondamentali in #gsped, #topic/key-concept
	  {{query (page-tags [[topic/key-concept]])}}
	- Guida all'uso di #[[Guida d'uso LogSeq]] si trova a [questa pagina]([[Guida d'uso LogSeq]])
	- Guida d'uso al framework #models/gsped/codeigniter
	- [[Guida d'uso Jira per utenti]]