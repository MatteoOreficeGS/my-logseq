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
  query-properties:: [:type :description :block :page :subject :tags]
  #+BEGIN_QUERY
  { :title [:h1 "Azioni"]
    :query [:find (pull ?b [ * ])
            :where
            [?b :block/refs ?page]
         [?page :block/properties ?props]
  [(get ?props :type) ?type]
  [(= ?type #{"LS/Tag/Action"})]
  [?b :block/properties ?bprops]
  		        [(get ?bprops :template "nil") ?bs]
  		        [(= ?bs "nil")]
    ]
  :table
    [:block/name
     [:page-property :type]]
  }
  #+END_QUERY