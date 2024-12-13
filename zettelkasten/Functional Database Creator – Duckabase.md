**Created** – 2023-10-05 17:21
**Status** – #idea
**Tags** – [[App]]

---

Ho immaginato di creare gli schemi di un database con questa sorta di sintassi, in modo da creare qualcosa di semplice, human readable.

Di base è un linguaggio per costruire schemi di validazione, nell'ottica di costruirci poi sopra una UI.

Reference: [[Inventare notazioni]] [[Information Design]]

```haskell

-- schema creation
s :: ( String -> [ Fields ] ) -> ( [ Values ] -> Record )

userSchema = s "user" [
	v "age" int [ (min 18), required ],
	v "name" string [ required, (min 5) ],
	n "links" "labeledUrl",
	r "tasks" "task",
	m "greet" ( \ctx => "Hello " ++ ( get "name" $ this ctx ) )
]


-- record creation

userA = userSchema [
	("age", 18),
	("name", "Gigi")
	("links", [
		{ label: "Sito", href: "gigi.com" },
		{ label: "Portfolio", href: "gigi.com/portfolio" }
	])
]
```

```haskell
newtype FieldName = String

-- value field
v :: FieldName -> Constructor -> [ Refiner ] -> ( a -> Maybe a )
newtype Constructor = Maybe a -> Maybe a
newtype Refiner = Maybe a -> Maybe a

-- relation field
r :: FieldName -> FieldName -> ( [ ID ] -> a )
newtype ID = String

-- nested field
n :: FieldName -> TemplateName -> ( a -> Maybe a )
newtype TemplateName = String

-- method field (a getter)
-- - This returns the current element
-- - DB returns the whole application context
m :: FieldName -> ( CTX -> c ) -> c 
data CTX = CTX {
	this :: This,
	db :: DB
}
```