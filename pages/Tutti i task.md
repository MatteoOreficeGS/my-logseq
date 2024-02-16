query-sort-by:: page
query-table:: true
query-sort-desc:: true
#+BEGIN_QUERY
{:title “:date: NEXT”
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

-