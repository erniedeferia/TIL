# Laziness & Exceptions

Say you have a form which can generate an exceptions in the process of returning a lazy sequence.

```
(defn can-explode-lazily
 []
  (get-db-objects ...) ;; this form would return a lazy sequence from, say, a database query. 
 )
```

To protected your caller from the possible exception thrown by (get-db-objects) you might be tempted to:

```
(defn can-explode-lazily
 []
 (try
   (get-db-objects ...)
   (catch TheExceptionType e () ) ) ) 
```

Except that sequences in Clojure are lazy by nature. In this case, the results of (get-db-objects) are not
evaluated until the sequence is consumed by the caller - too late for the (try/catch) form to be effective.

The solution is to force the evaluation of the sequence:

```
(defn can-explode-lazily
 []
 (try
   (doall 
   (get-db-objects ...) )
   (catch TheExceptionType e () ) ) ) 
```

In this case we use `doall` to force the side effect caused by traversing the lazy sequence and storing
the entire result in memory. 



