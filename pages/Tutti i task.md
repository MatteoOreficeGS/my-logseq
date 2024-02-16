query-sort-by:: page
query-table:: true
query-sort-desc:: true
#+BEGIN_QUERY
{:title “ALL TASKS”
:query [:find (pull ?h [*])
:in $ ?start ?next
:where
[?h :block/marker ?marker]
[(contains? #{“NOW” “LATER” “TODO”} ?marker)]
[?h :block/page ?p]
[?p :block/journal? true]
[?p :block/journal-day ?d]
[(> ?d ?start)]
[(< ?d ?next)]]
:inputs [:today :7d-after]
:collapsed? false}]}
#+END_QUERY

- #+BEGIN_QUERY
  {:title [:h3 "🔥 Tasks past due"]
   :query [:find (pull ?b [*])
   :where
     [?b :block/marker ?m]
     (not [(contains? #{"DONE" "CANCELED"} ?m)])
     [?h :block/page ?p]
     [?p :block/journal? true]
   ]
   :table-view? true
  }
  #+END_QUERY