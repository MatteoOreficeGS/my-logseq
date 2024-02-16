query-sort-by:: page
query-sort-desc:: false
#+BEGIN_QUERY
{:title [:h3 "All Tasks"]
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
