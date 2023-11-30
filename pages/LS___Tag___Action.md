type:: [[LS/Class]]
description:: Descrive una azione da eseguirsi
subject:: Soggetto opzionale che deve eseguire l'azione

- # Tipi di azione
  query-sort-by:: block
  query-table:: true
  query-sort-desc:: false
  query-properties:: [:block :page :description :created-at :updated-at :type]
  {{query (page-property :type [[LS/Tag/Action]])}}
-
- Provap
  type:: [[LS/Tag/Action]]
- query-sort-by:: type
  query-table:: true
  query-sort-desc:: true
  query-properties:: [:type :description :block :page]
  #+BEGIN_QUERY
  { :title [:h1 "Azioni"]
    :query [:find (pull ?b [ * ])
            :where
            [?b :block/refs ?page]
         [?page :block/properties ?prop]
  [(get ?prop :type) ?type]
  [(= ?type #{"LS/Tag/Action"})]
    ]
  }
  #+END_QUERY