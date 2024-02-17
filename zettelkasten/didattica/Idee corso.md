- Far ragionare su input -> output
- Controllare esercizi di Lussu

Esempio di esercizio
- scomposizione "a ritroso" di quello che serve per il GTL.
- quindi, immaginare la lista delle operazioni che servono per arrivare alla font

Fare diversi esercizi di visualizzazione di algoritmo
- diagramma
- descrizione testuale (evidenziando i termini chiave)
- notazione immaginaria

Esempio di scomposizione:
```ts
type GTLInput = {
	sintassi: Record<Simbolo, Forma>
	composizioni: Array<Glifo>
	metriche: Metriche
}

type Simbolo = string

type Forma = (glifo: Glifo, area:Area, parametri: Parametri) => Array<Contorno>

type Glifo = {
	name: NomeUnicode
	structure: Structure
}

type Structure = Array<Array<String>>

type NomeUnicode = string

// -- Oltre un certo punto, i tipi sono definiti dal "sistema" -- //

type Contorno = Array<Operazione>

type Operazione = MoveTo | LineTo | CurveTo

type MoveTo = Punto

type LineTo = Punto

type CurveTo = {
	handle_1: Punto
	handle_2: Punto
}

type Punto = {
	x: number,
	y: number
}

type Dimensione = {
	w: number,
	h: number
}

type Metriche = {
	x_height: number
	ascender: number
}

type Area = Punto & Dimensione

type Parametri = Record<string, unknown>
```