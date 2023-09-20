**Created** – 2023-09-19 17:18
**Status** – #idea
**Tags** –

---

Utilizzare pseudo-codice per definire il funzionamento dell'applicazione
E usare l'AI per convertirlo in codice reale.

Un esempio:
```
from 'nanoid' import { nanoid }
// use this for generating IDs

---

@type Direction = 1 | -1
// 1: Clockwise
// -1: Counterclockwise

---

@interface NodeData
	id: string

@interface PointData
	nodeId: string
	direction: Direction

@interface PathData
	id: string
	points: Array<PointData>
	closed: boolean

@interface AppData
	nodes: Array<NodeData>
	paths: Array<PathData>

---

@class Path implements PathData
  points: Array<PointData>

	constructor(
		data: Partial<PathData>
	)

	addPoint(
		point: PointData
	)

---

@class App implements AppData
  paths: Array<Path>
  nodes: Array<NodeData>

  constructor(
		data: Partial<AppData>
	)
  - description:
    - uses PathData in 'data' to initialize 'paths'

	createPath() => Path
	getPath(id: string) => Path | undefined
	deletePath(id: string) => void

	createNode() => Node
	getNode(id: string) => Node | undefined
	deleteNode(id: string) => void

	exportData() => AppData
	- description:
		- returns AppData from this.nodes and this.paths
		- converts this.paths to Array<PathData>
		

	importData(data: AppData) => void
	- description:
		- same as what the constructor does
		- deletes previous this.paths and this.nodes
```