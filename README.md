# Delegate

A Clojure library offering a single macro `delegate`. 
Delegate can be used for proxying over an object (anonymous or otherwise) but
selectively overriding the behavior of certain functions when those functions 
are invoked against the delegating view. This is a pattern that some Java developers
leverage quite a bit and sometimes I find myself wanting it in Clojure when doing
heavy interop.


```clojure

(def t "Test")

(def d 
  (delegate t 
    Object
      (toString 
        (str "Delegate Test!"))))

(print d)
; Delegate Test!

(print (.length d))
; 4

```


