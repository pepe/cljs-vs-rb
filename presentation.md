---
author: Pepe
date: 2017-11-09
title: Clojure(Script) pohledem rubisty
---

# Clojure(Script)           Pohledem              Rubisty

---

## Kdo jsem?

* @pepe
* @damnpepe
* První Rubista

---

## Co je Clojure?

* Datově zaměřený …
* Funkcionální …
* Praktický …
* … jazyk

---

## Datové zaměření

* Skvělé literály
* Převážně neměnné
* Lehké transformace

---

## Funkcionálno

* Facelifted Lisp 
* Konkurentní
* I v Ruby

---

## Praktičnost

* REPL
* Jednoduchost
* Stejně jako Ruby

---

## ClojureScript

* JSVM
* React.js
* HTML as Data


---

## Reaktivní 

* Potok
* RxJS
* C#

---

## Stále jste tady?

---

## Ukaž Kód!

```
(for [{:slide/keys [order type bullets 
                    title text image code]} slides]
  [:div.slide
    {:key order :class (name type)}
    [:h1.title title]
    (case type
      :type/bullets [:ul (for [bullet bullets]
                            [:li {:key bullet} bullet])]
      :type/text    [:p text]
      :type/image   [:div [:img {:src image}]]
      :type/code    [:pre code])])
```

---

## Víc Kódu!

```
(defrecord ^:private SetSlidesCount [count]
  ptk/UpdateEvent
  (update [_ state]
    (assoc state :deck/slides-count count)))

(deftype NavigatePreviousSlide []
  ptk/WatchEvent
  (watch [_ {slide :slide/current} _]
    (rxt/just (->SetCurrentSlide (dec slide)))))
    
```

---

## Sponzorské sdělení

```
https//github.com/laststar/showrum
https//github.com/pepe/clsj-vs-ruby
```
