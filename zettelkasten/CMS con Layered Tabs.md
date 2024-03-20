---
riferimenti:
  - "[[App]]"
---
---

Gestire l'url: 

- Rest parameter, it's dynamic (needs server)
```
${base} / [ ... sequence ]

so ${base} / coll-1 / coll-2 / coll-3
```

- Query param (works on static apps)
```
?stack="collection-1"&stack="collection-2"&stack="collection3"
```

Navigation means basically adding and removing items to the stack.

---

Ottimo per quando si vanno a gestire relazioni profondamente innestate.

![[cms-layers-tabs.jpg]]