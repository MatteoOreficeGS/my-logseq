query-sort-by:: page
query-sort-desc:: true
#+BEGIN_QUERY
{:title [:h3 "🔥 Tasks past due"]
 :query [:find (pull ?b [*])
 :where
   [?b :block/marker ?m]
   (not [(contains? #{"DONE" "CANCELED"} ?m)])
   [?b :block/page ?p]
   [?p :block/journal? true]
 ]
 :table-view? true
}
#+END_QUERY
