type:: [[LS/Class]]
description:: Descrive una azione da eseguirsi
subject:: soggetto opzionale che deve eseguire l'azione

- # Azioni disponibili
  query-sort-by:: block
  query-table:: true
  query-sort-desc:: false
  query-properties:: [:block :page :description :created-at]
  {{query (page-property :type [[LS/Tag/Action]])}}
- # Template
	- template:: Action
	  template-including-parent:: true
	  type:: [[LS/Tag/Action]]
	  description:: inserire la descrizione di questa azione