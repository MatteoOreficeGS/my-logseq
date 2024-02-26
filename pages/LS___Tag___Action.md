type:: [[LS/Class]]
description:: Descrive una azione da eseguirsi
subject:: Soggetto opzionale che deve eseguire l'azione

- # Tipi di azione
  query-sort-by:: block
  query-table:: true
  query-sort-desc:: false
  query-properties:: [:block :page :description :created-at :updated-at :type]
  {{query (page-property :type [[LS/Tag/Action]])}}
- query-sort-by:: type
  query-table:: true
  query-sort-desc:: false
  query-properties:: [:type :description :block :page :subject]
  #+BEGIN_QUERY
  { :title [:h1 "Azioni"]
    :query [:find (pull ?block [ * ])
            :where
            [?block :block/properties ?props]
  [(get ?props :template) ?template]
  (not [(= ?template "")])
  
    ]
  }
  #+END_QUERY