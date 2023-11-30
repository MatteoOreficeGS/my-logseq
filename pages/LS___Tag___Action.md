type:: [[LS/Class]]
description:: Descrive una azione da eseguirsi
subject:: Soggetto opzionale che deve eseguire l'azione

- # Azioni disponibili
  query-sort-by:: block
  query-table:: true
  query-sort-desc:: false
  query-properties:: [:block :page :description :created-at]
  {{query (page-property :type [[LS/Tag/Action]])}}
- # Template
	- template:: TagAction
	  template-including-parent:: true
	  type:: [[LS/Tag/Action]]
	  description:: inserire la descrizione di questa azione