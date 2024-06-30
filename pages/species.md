tags:: species, class

- [[plants]] and [[plants/species]]
- [[shrooms]]
- [[animals]]
- collapsed:: true
  #+BEGIN_QUERY
  {
    :title "Blocks from Pages with 'keyword' in their names"
    :query [
      :find (pull ?b [*])
      :where
      [?p :page/name ?pname]
      [(clojure.string/includes? ?pname "edem")]
      [?b :block/page ?p]
    ]
    :result-transform (fn [result]
                        (distinct result))
  }
  #+END_QUERY
-
- {{query (and (page-tags [[species]]) (not (page-tags [[class]])))}}
  query-sort-by:: page
  query-sort-desc:: false
  query-properties:: [:page :alias :updated-at :availability :created-at]