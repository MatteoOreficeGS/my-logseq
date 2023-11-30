type:: [[LS/Class]]
description:: Descrive una azione da eseguirsi
subject:: Soggetto opzionale che deve eseguire l'azione

- # Tipi di azione
  query-sort-by:: block
  query-table:: true
  query-sort-desc:: false
  query-properties:: [:block :page :description :created-at]
  {{query (and (property :type [[LS/Tag/Action]]) (not))}}
- # Azioni
  query-table:: true
  {{query (and (property :type [[LS/Tag/Action]]) (not))(property :type [[LS/Tag/Action]])}}