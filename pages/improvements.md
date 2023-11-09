# Scopo
- Pagina utilizzata per trovare i **backlink** a questo **tag**
- Pagina utilizzate per elencare direttamente degli improvements
- # Proposte di miglioramento
	- query-sort-by:: page
	  query-table:: true
	  query-sort-desc:: true
	  query-properties:: [:block :page]
	  #+BEGIN_QUERY
	     {:title [:h3 "TODOs for this Project:"]
	      :query [:find (pull ?b [*])
	              :where
	              [?child :block/parent ?b]
	              [?b :block/refs ?p]
	              [?p :block/name "improvements"]           
	  ]
	      :remove-block-children? false
	  }
	  #+END_QUERY