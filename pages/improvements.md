# Scopo
- Pagina utilizzata per trovare i **backlink** a questo **tag**
- Pagina utilizzate per elencare direttamente degli improvements
- # Proposte di miglioramento
	- query-sort-by:: page
	  query-table:: true
	  query-sort-desc:: false
	  #+BEGIN_QUERY
	  {:title "All blocks tagged using current page"
	   :query [:find (pull ?b [*])
	         :in $ ?current-page
	         :where
	         [?p :block/name ?current-page]
	         [?b :block/path-refs ?p]
	  ]
	   :inputs [:current-page]}
	  #+END_QUERY