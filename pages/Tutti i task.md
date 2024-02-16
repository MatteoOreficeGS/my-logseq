query-sort-by:: page
query-table:: true
query-sort-desc:: true
#+BEGIN_QUERY
{:title “ALL TASKS”
:query [
   :find (pull ?h [*])
   :where
[?h :block/marker ?marker]
[(contains? #{“NOW” “LATER” “TODO”} ?marker)]
[?h :block/page ?p]
[?p :block/journal? true]
:collapsed? false}]
}
#+END_QUERY

-