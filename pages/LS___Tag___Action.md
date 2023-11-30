type:: [[LS/Class]]
description:: Descrive una azione da eseguirsi
subject:: Soggetto opzionale che deve eseguire l'azione

- # Tipi di azione
  query-sort-by:: block
  query-table:: true
  query-sort-desc:: false
  query-properties:: [:block :page :description :created-at]
  {{query (page-property :type [[LS/Tag/Action]])}}
-
- # Azioni
  query-table:: true
- *#+BEGIN_QUERY*
  {:title "funcking example"
    :query [:find (pull ?b [*])
            :where
            [?p :block/name "project"]
            [?par :block/refs ?p]
            [?b :block/parent ?par]
            [?b :block/marker ?marker]
            [(contains? *#{"TODO"} ?marker)]*
    ]
  }
  *#+END_QUERY*