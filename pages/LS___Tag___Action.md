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
- query-table:: true
  #+BEGIN_QUERY
  { :title "Current Members"
    :query [:find (pull ?b [*])
            :in $ ?current-page
            :where
            [?b :block/page ?p]
            [?p :block/name ?current-page]
            [?b :block/parent ?parent]
            [?parent :block/content "Members"]]
    :inputs [:current-page] }
  #+END_QUERY