query-sort-by:: page
query-table:: true
query-sort-desc:: true
#+BEGIN_QUERY
{:title “ALL TASKS”
:query [
   :find (pull ?h [*])
   
   :collapsed? false
]}
#+END_QUERY

-