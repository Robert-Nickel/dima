# Primzahlen

Primzahlen < 100: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97

Primzahlen sind sowas wie Atome.

Eine Zahl die keine Primzahl ist, ist eine zusammengesetzte Zahl, da sie auf eindeutige Weise aus Primzahlen zusammengesetzt ist.

Beispiel: `38`

`36 / 2 = 18` <- 2 merken

`18 / 2 = 9` <- 2 merken

`9 / 3 = 3` <- 3 merken

`3 / 3 = 1` <- 3 merken

=> `36` = `2 * 2 * 3 * 3` = `2^2 * 3^2`

Weg von Atomen zu zusammengesetzter Zahl leicht, Rückweg (Primfaktorenzerlegung) schwierig (in NP), daher gut für kryptografische Anwendungen. Fun Fact: Härtester Fall, wenn die Zahl aus 2 ungefähr gleich großen Primzahlen zusammengesetzt ist.

Man muss alle Primzahl bis zur Wurzel der Zahl, die zerlegt werden soll, ausprobieren. Um zu prüfen, ob eine Zahl eine Primzahl ist, kann man also die Wurzel der Zahl nehmen, und schauen, ob die Zahl durch eine der Zahlen zwischen 2 und der Wurzel teilbar ist. Wenn sie das nicht ist, dann ist sie eine Primzahl.

*Beispiel*:

`101` eine Primzahl?

`Wurzel aus 101 =~10`

`101` durch `2`, `3`, `5` oder `7` teilbar? Nein. Also ist 101 eine Primzahl.

Goldbach'sche Vermutung: Jede gerade Zahl ist die Summe von 2 Primzahlen.

Zwillingsprimzahlen Vermutung: Es gibt unendliche viele Primzahlen, bei denen die Zahl + 2 auch eine Primzahl ist. (z.B. 3 und 5 oder auch 29 und 31)

## Größter gemeinsamer Teiler

Die größte Zahl, die `a` und `b` teilt.

| `a` | `b` | ggt |
| --- | --- | --- |
| 5   | 5   | 5   |
| 8   | 12  | 4   |
| 22  | 15  | 1   |
| 4   | 8   | 4   |

Man multipliziert alle gemeinsamen Primfaktoren mit dem jeweils niedrigeren Exponenten, um den ggt zu berechnen.

Wenn es nach der Primfaktorzerlegung des Zahlen keine gemeinsamen Primfaktoren gibt, dann ist der ggt immer 1 und die Zahlen sind teilerfremd.


`8` = `2^3` und `12` = `2^2 * 3^1`

=> ggt = `2^2` = `4`

`500` = `2^2 * 5^3` und `120` = `2^3 * 3 * 5`

=> ggt = `2^2 * 5` = `20`

## Kleinstes gemeinsames Vielfaches

Die kleinste Zahl, die von zwei Zahlen `a` und `b` geteilt wird.

| `a` | `b` | kgm |
| --- | --- | --- |
| 5   | 5   | 5   |
| 8   | 12  | 24  |
| 22  | 15  | 330 |

Man multipliziert alle (nicht nur die gemeinsamen!) Primfaktoren mit dem jeweils höheren Exponenten, um den kgv zu berechnen.

Wenn es keine gibt, dann ist das Produkt der Zahlen das kgv.

`95256` = `2^3 * 3^5 * 7^2` und `432` = `2^4 * 3^3`

=> kgv = `2^4 * 3^5 * 7^2` = `190512`

## Euklidischer Algorithmus

Wird genommen zur Berechnung des ggt, da Primfaktorzerlegung teuer ist.


___
[Vorheriges: Diskrete Exponentialfunktion](diskrete-exponentialfunktion.md) | [Nächstes: unklar](unklar.md)