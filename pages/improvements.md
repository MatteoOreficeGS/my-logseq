# Scopo
- Pagina utilizzata per trovare i **backlink** a questo **tag**
- Pagina utilizzate per elencare direttamente degli improvements
- # Proposte di miglioramento
	- query-sort-by:: page
	  query-table:: true
	  query-sort-desc:: true
	  query-properties:: [:block]
	  #+BEGIN_QUERY
	     {:title [:h3 "TODOs for this Project:"]
	      :query [:find (pull ?b [*])
	              :where
	              [?b :block/refs ?p]
	              [?p :block/name "improvements"]           
	  ]
	      :breadcrumbs-show? true
	      :collapsed? false}
	  #+END_QUERY