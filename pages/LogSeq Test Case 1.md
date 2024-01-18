# Richiesta 1
- ## Playground
	- a block found by search
	  tags:: mytag
	  myprop:: val1, val2, val3
	- a second block found by search
	  tags:: mytag
	  myprop:: val4, val5, val1
- ## Query
	- #+BEGIN_QUERY
	  {
	   :query [:find ?myprop-vals
	     :where
	       [?tag :block/original-name "mytag"]
	       [?b :block/refs ?tag]
	       [?b :block/properties ?props]
	       [(get ?props :tags) ?tags]
	       [(contains? ?tags "mytag")]
	       [(get ?props :myprop) ?myprop-vals]
	   ]
	   :view (fn [vals]
	     (for
	       [d
	         (distinct (flatten (map
	           (fn [val]
	             (clojure.string/split val " ")
	           )
	           vals
	         )))
	       ]
	       [:div d]
	     )
	   )
	  }
	  #+END_QUERY
	-
	-