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
- Provap
  type:: test
- # Azioni
  query-table:: true
- query-sort-by:: block
  query-table:: true
  query-sort-desc:: true
  query-properties:: [:block :page]
  #+BEGIN_QUERY
  { :title "Current Members"
    :query [:find (pull ?block [ * ])
            :where
            [?block :block/content ?blockcontent]
  [?block :block/page ?page]
  [?page :block/name ?pagename]
  
    ]
  }
  #+END_QUERY