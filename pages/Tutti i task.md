query-sort-by:: page
query-table:: true
query-sort-desc:: true
#+BEGIN_QUERY
{:title [:h3 "🧭️ Tasks By Month"]
 :query [:find ?dYYYYMM (count ?b)
       :keys type number
       :in $ ?start ?end
       :where   
       (task ?b #{"LATER" "TODO" "DOING"})
       (or [?b :block/scheduled ?d] [?b :block/deadline ?d])
       [(str ?d) ?ds]
       [(subs ?ds 0 6) ?dYYYYMM]       
       ]
 :inputs [:-1w :+60m]
:collapsed? false
 :group-by ?d
 :view (fn [rows]
       [:table
        [:thead [:tr [:th "Month"] [:th "Count"]]]
        [:tbody
         (let [sorted-rows (sort-by :type rows)]
           (for [r sorted-rows]
             [:tr
              [:td (get-in r [:type])]
              [:td (get-in r [:number])]]))]])
}
#+END_QUERY

-