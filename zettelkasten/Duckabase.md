**Created** – 2023-10-05 17:56
**Status** – #idea
**Tags** – [[App]] [[Functional Database Creator – Duckabase]]

---

Un'applicazione per costruire database, secondo il principio del duck typing.

- In questo database i singoli field sono definiti indipendentemente dal data model.
- I diversi data model selezionano i field esistenti.
- Questo significa che due data model che utilizzano lo stesso field sono confrontabili rispetto a quel field
- Ulteriormente, è possibile creare un'interfaccia (à la TS) dove specifico quali field ci sono, e tutti i modelli che hanno quei field fanno parte di quella interfaccia.
	- In questo modo il database utilizza il concetto di Duck Typing