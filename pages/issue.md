filters:: {"done" false}

- {{query (namespace [[issue]])(sample 3)}}
  query-properties:: [:page :description]
  query-sort-by:: page
  query-sort-desc:: false
- # Definizione
	- Una **issue** rappresenta un problema che si é manifestato ed é da risolvere #INFO
		- Si rivolve di solito solo quando si manifesta
		- Interessa una parte esistente, es: classe OOP, microservizio, controllo UI, etc.
		- Non é un #improvements
- # Scopo
- Tag page che consente di trovare tutte le issue riscontate
- LATER Utilizzare il documento [Linee guida sviluppo](https://docs.google.com/document/d/1a7bF6bTtYzgwUMKCcsmfhycHUbsjbBHsOpT1MGEvvNg/edit?pli=1#heading=h.qb8anohdadd2) per riportare in LogSeq altri tipi di issue con migliore organizzazione