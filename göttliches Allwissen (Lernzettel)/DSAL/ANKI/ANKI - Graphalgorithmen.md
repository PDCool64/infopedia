TARGET DECK: DSAL::Graphalgorithmen

DFS,BFS #flashcard
Finden von Pfaden
$\mathcal{O}(\left| V \right|+\left| E \right|)$
<!--ID: 1785329529995-->


Sharir's Algorithmus #flashcard
SCCs in gerichteten Graphen
$\mathcal{O}(\left| V \right|+\left| E \right|)$
<!--ID: 1785329530001-->


Prims Algorithmus #flashcard
Minimaler Spannbaum
<!--ID: 1785329530008-->


Bellman-Ford #flashcard
SSSP mit negativen Kantengewichten
$\mathcal{O}(\left| V \right|\cdot \left| E \right|)$
<!--ID: 1785329530015-->


Dijkstra #flashcard
SSSP *ohne* negative Kanten
$\mathcal{O}(\left| V \right|^{2})$ (naive)
schneller als Bellman ford falls anwendbar
<!--ID: 1785329530023-->


Warshall #flashcard
Transitive Hülle
$\Theta(\left| V \right|^{3})$
<!--ID: 1785329530031-->


Floyd (aka. Floyd-Warshall) #flashcard
APSP (kann negative Zyklen aber nicht behandelt)
$\mathcal{O}(\left| V \right|^{3})$
<!--ID: 1785329530077-->


Ford-Fulkerson #flashcard
Max-Flow/Min-Cut
$\mathcal{O}(\left| f^{*} \right|\cdot \left| E \right|\cdot \left| V \right|)$ mit $\left| f^{*} \right|$ als Wert des Maximalen Flusses
<!--ID: 1785329530082-->


Edmonds-Karp #flashcard
Max-Flow/Min-Cut
wählt mit Breitensuche einen augmentierenden Pfad mit minimale Anzahl Kanten
$\mathcal{O}(\left| V \right|\cdot \left| E \right|^{2})$
<!--ID: 1785329583908-->
