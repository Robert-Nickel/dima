# Permutationen und Kombinationen
## Permutationen
*Beispiel:* Zehn Bücher werden in einem Regal angeordnet, also gibt es

`10 * 9 * 8 * 7 * 6 * 5 * 4 * 3 * 2 * 1` = `10!` = _`3_628_800`_

Möglichkeiten, denn für den ersten Platz kommen 10 Bücher in Frage, für den zweiten Platz 9 etc.

*Beispiel*
Die ersten 3 Plätze des Marathons werden üblicherweise durch die bereits bekannten 10 besten Läufer belegt. Also gibt es

`10 * 9 * 8` = `720`

Möglichkeiten für das Siegerpodest.

Definition: Eine Permutation ist eine Menge von unterschiedlichen Elementen in einer sortierten Reihenfolge.
Im Marathon-Beispiel nennt man die Permutation eine 3-Permutation der 10 besten Läufer.

Die mögliche Anzahl für Permutationen ist

`P(n,k) = n * (n -1) * (n - 2) * ... * (n - k + 1)`

= `n! / (n - k)!`

`k` ist die Größe des Siegerpodest  
`n` ist die Anzahl der in Frage kommenden Läufer

`10! / (10 - 3)!`

= `10! / 7!`

= `10 * 9 * 8`

= __`720`__

*Beispiel:*
Wie viele Permutationen existieren für die Buchstabenfolge `ABCDEFGH`, in denen `ABC` vorkommt?

Lösung: `ABC` wird als ein Objekt gesehen, die anderen 5 Buchstaben als individuelle Objekt. Also existieren 6 Objekte, die beliebig angeordnet werden können. 

`6!` = `720`

## Kombinationen
