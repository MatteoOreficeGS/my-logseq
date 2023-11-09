# Scopo
- Pagina utilizzata per trovare i **backlink** a questo **tag**
- Pagina utilizzate per elencare direttamente degli improvements
- # Proposte di miglioramento
	- query-sort-by:: page
	  query-table:: true
	  query-sort-desc:: false
	  #+BEGIN_QUERY
	     {:title [:h3 "TODOs for this Project:"]
	      :query [:find (pull ?b [*])
	              :where
	              [?b :block/ref-pages ?p]
	              [?p :block/name "5918"]
	              [?b :block/marker ?marker]
	              [(contains? #{"TODO" "DOING"} ?marker)]
	  ]
	      :breadcrumbs-show? true
	      :collapsed? false}
	  #+END_QUERY