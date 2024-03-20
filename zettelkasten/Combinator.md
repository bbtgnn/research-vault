---
riferimenti:
  - "[[App]]"
---
---

- Voglio combinare 4 cose: A, B, C, D
- Ogni cosa ha varianti
- Voglio specificare quali combinazioni di varianti e di cose non vanno bene
- Lasciare combinare il resto

Es: 
```
{
	"A": ["A1", "A2", ...],
	"B": [...],
	...
	"rules": [
		"No A1 + B3",
		...
	]
}
```

