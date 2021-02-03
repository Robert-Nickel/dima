# Ganzzahlige Division

## Teilen und Teiler

*Beispiele der 3. Klasse:*

5 Leute teilen sich einen Kasten Bier (20 Flaschen). Also kriegt jeder 4 Flaschen (20 / 5 = 4).

3 Leute teilen sich einen Kasten Bier (20 Flaschen). Also kriegt jeder 6 Flaschen, und 2 Flaschen bleiben übrig.

Bei ganzen Zahlen teilt eine Zahl die andere (bzw. ist ein Teiler dieser Zahl), wenn das Ergebnis selbst eine ganze Zahl ist. 

Schreibweise: `5 | 20` (5 teilt 20) oder `3 /| 20` (3 teilt 20 nicht, den Strich durchstreichen)

## Eigenschaften von Teilern

Seien `n` und `d` positive ganze Zahlen.

Dann gibt es `Abrunden(n/d)` viele positive ganze Zahlen, die `n` nicht überschreiten und durch `d` teilbar sind.

*Beispiel:*

`n = 100`, `d = 3`

= `Abrunden(100 / 3)`

= `Abrunden(33,3...)`

= `33` 

# Modulo

## Division mit Rest

Satz: Für jedes `a ∈ Z` und `m ∈ N` gibt es eindeutige Zahlen `q ∈ Z` und `r ∈ N0` mit `0 ≤ r < m`, so dass

`a = m * q + r`

`a` = Divident (Das Zu-teilende), `m` = Divisor (Durch was geteilt wird)

`q` = Quotient (Ergebnis der Teilung), `r` = Rest

Mit anderen Worten: Bei einer Teilung gibt es immer genau ein Ergebnis, welches aus Quotient und Rest besteht.

Für feste `m` werden die Funktionen `div` und `mod` so definiert:

`r = a mod m`

`q = a div m`

*Beispiele:*
`17 mod 5: 3 * 5 + 2 also 2`

`-17 mod 5: -4 * 5 + 3 also 3`

`3 mod 5: 0 * 5 + 3 also 3`

`-3 mod 5: -1 * 5 + 2 also 2`

[Guter Onlinerechner für ganzzahlige Division und Rest](https://www.symbolab.com/solver/modulo-calculator)

## Kongruenz

Wenn 2 ganze Zahlen `a` und `b`, die durch `m` geteilt werden, den gleichen Rest haben, dann sind sie zueinander __kongruent__ für diesen Divisor.

Schreibweise: 

Kongruenz: `a ≡ b (mod m)`

Nicht-Kongruenz: `a /≡ b (mod m)` (das Kongruenzsymbol durchstreichen)

Diese Schreibweise beschreibt ein Verhältnis, im Gegensatz zur Funktion `r = a mod m`

*Beispiele:*

`22 ≡ 17 (mod 5)`, da `22 mod 5 = 2` und `17 mod 5 = 2`

`22 /≡ 17 (mod 54)`, da `22 mod 4 = 2` und `17 mod 4 = 1`

2 ganze Zahlen `a` und `b` und die natürliche Zahl `m` sind nur kongruent, wenn es eine ganze Zahl `k` gibt, so dass
1. `a`-`b` = `k * m`
2. `a` = `b + k * m`

*Beispiele:*

`a = 17`

`b = 5`

`m = 6`

`17 - 5 = k * 6`

= `12 = k * 6` wahr für `k = 2` => kongruent

`a = 24`

`b = 14`

`m = 6`

`24 = 14 + k * 6`

= `10 = k * 6` falsch => nicht kongruent

## Restklassen

Wenn zwei ganze Zahlen `a` und `b` für ein `m` kongruent sind, dann herrscht eine Äquivalenzbeziehung zwischen ihnen, d.h. sie sind
- symmetrisch (man kann sie vertauschen)
- reflexiv (d.h. wenn `a` und `b` die gleiche Zahl ist, ist es immer kongruent)
- transitiv (d.h. wenn `a` und `b` zueinander kongruent sind und `b` und `c` zueinander kongruent sind, dann sind auch `a` und `c` zueinander kongruent).

Durch die Äquivalenz entstehen die Restklassen `Rm`, z.B. für `m = 5`

`[0]5 = {..., -10, -5, 0, 5, 10, ...}`

`[1]5 = {..., -9, -4, 1, 6, 11, ...}`

`[2]5 = {..., -8, -3, 2, 7, 12, ...}`

`[3]5 = {..., -7, -2, 3, 8, 13, ...}`

`[4]5 = {..., -6, -1, 4, 9, 14, ...}`

=> alle ganzen Zahlen `a`, die `a mod m = 0` ergeben.  

Die Menge `Zm` = `{0, 1, 2, ..., m - 1}`
- Repräsentiert die entsprechenden Restklassen, da die Restklassen danach wieder von vorne anfangen, z.B. `[0]5 = [5]5`
- Bildet die Menge der möglichen Restwerte

*Lifehack*: Wenn man Modulorechnung beschleunigen will, kann man sich kleinere Repräsentanten der gleichen Äquivalenzklasse suchen.

## Algebraische Strukturen mit Rest

`(a + b) mod m` = `a (+m) b`

`(a * b) mod m` = `a (*m) b`

bzw.

![](/bilder/modulo-algebra.png)

| `(+3)` |   0   |   1   |          2           |
| :----: | :---: | :---: | :------------------: |
|   0    |   0   |   1   |          3           |
|   1    |   1   |   2   |          0           |
|   2    |   2   |   0   | 1 (da `2 + 2 mod 3`) |

Fun Fact: 0 ist das neutrale Element

Inverses Elemtent: Was uns wieder zur 0 zurückbringt bzw. zu jedem `x` gibt es ein `-x`. Schreibweise auch: `x^-1`

Wenn `d` das additive Inverse von `e` ist, dann gilt:

`e (+m) d = 0`

= `d = m - e` (falls `e != 0`, sonst `d = 0`)

z.B. `2 = 3 - 1`

In diesem Beispiel: 1 und 2

| `(*3)` |   0   |   1   |          2           |
| :----: | :---: | :---: | :------------------: |
|   0    |   0   |   0   |          0           |
|   1    |   0   |   1   |          2           |
|   2    |   0   |   2   | 1 (da `2 * 2 mod 3`) |

Fun Fact: 1 ist das neutrale Element

Inverses Element: Was uns wieder zur 1 zurückbringt z.B. 2 und 2

Existiert immer, wenn `e` und `m` teilerfremd sind (also es keine natürliche Zahl außer 1 gibt, die beide Zahlen teilt, ist bei Primzahlen immer der Fall). 

`(Zm, (+m), (*m))` ist ein Restklassenring aber kein Restklassenkörper, da die inversen Elemente der Multiplikation fehlen. Anderer Zahlenring sind die ganzen Zahlen.

Ein Restklassenring befolgt teilweise die gewohnten Rechenregeln, aber nicht alle. Befolgt:
- Assoziativgesetz für + und * (z.B. `(a * b) * c` = `a * (b * c)`)
- Distributivgesetz (`a * b + a * c` = `a * (b + c)`)
- Neutrales Element existiert
- Additives Inverses existiert, aber kein Multiplikatives Inverses für jede Zahl.

Befolgt nicht manche Eindeutigkeitssätze.

Ist `m` eine Primzahl, dann ist es darüber hinaus ein Restklassenkörper.

Ein Restklassenkörper ist eine Menge, in der alle Rechengesetze wie gewohnt gelten. Andere Beispiele sind Reele Zahle, Komplexe Zahlen etc.

`5 (+7) 3` = `(5 + 3) mod 7` = `1`

`3 (*7) 5` = `(3 * 5) mod 7` = `1`

## Verschiebealgorithmus

Um Multiplikatives Inverses zu finden.

Was ist das Inverse von `4` in `Z9`?

`1/4` ist keine ganze Zahl, also Zähler `+ 9`

`10/4` = `2,5` ist keine ganze Zahl, also Zähler `+ 9`

`19/4` = `4,75` ist keine ganze Zahl, also Zähler `+ 9`

`28/4` = `7` ist **eine** ganze Zahl, also `4^-1 in Z9` = `7`

Test: `7 (*9) 4` = `28 mod 9` = `1` ⬅️ neutrales Element ✅

Fun Facts:

`0` hat nie ein multiplikatives Inverses.

`1` ist immer sein eigenes multiplikatives Inverses (d.h. für jedes `m` gibt es ein Inverses für die 1, nämlich 1).

Die multiplikativen Inversen sind **immer eindeutig** wenn sie existieren. Das ist gut, wenn man nach dem Inversen sucht, und Zahlen ausschließen kann, weil sie bereits multiplikative Inverse anderer Zahlen in Z sind.

## Rechnen mit kongruenten Zahlen
Wenn `a ≡ b mod m` und `c ≡ d mod m`, dann

`a + c ≡ b + d mod m` bzw. `(a + b) mod m` = `((a mod m) + (b mod m)) mod m`

`a * c ≡ b * d mod m` bzw. `(a * b) mod m` = `((a mod m) * (b mod m)) mod m`

Man kann also bei Addition und Multiplikation auch erst die Bestandteile Modulorechnen und dann die Ergebnisse miteinander addieren/multiplizieren und dann nochmal Modulorechnen.

*Beispiel*:

`7 ≡ 2 mod 5` und `11 ≡ 1 mod 5`

=> `2 + 1 mod 5` = `3 mod 5` = `3`

oder für Multiplikation

=> `2 * 1 mod 5` = `2 mod 5` = `2`

Die Formel stimmt allerdings **nicht**, wenn `a`, `b`, `c` oder `d` ≡ 0 sind. Dann würde man durch 0 teilen, was nicht erlaubt ist.

# Zahlenrepräsentation

Es gibt unterschiedliche Repräsentationen *wow*

Im Dezimalsystem 123,456 bedeutet eigentlich

`1 * 10^2 + 2 * 10^1 + 3 * 10^0 + 4 * 10^-1 + 5 * 10^-2 + 6 * 10^-3`

## Umrechnung ins Dezimalsystem

1. Zahl wie oben zerlegen
2. Ausrechnen

*Beispiel*: 45,4 im Oktalsystem

1. `4 * 8^1 + 5 * 8^0 + 4 * 8^-1`
2. = `4 * 8 + 5 + 4 * 1/8` = `37,5`

## Umrechnung aus Dezimalsystem in ein anderes System
1. `b = Basis des anderen Zahlensystems`
2. `n1` ist die Zahl vor dem Komma
3. `n2` ist 0,die Zahl nach dem Komma
4. Vor dem Komma
   1. Teile `n1` durch `b`
   2. Nimm den Rest dieser Division als Stelle (ganz rechts) der neuen Zahl
   3. Wiederhole mit dem Ergebnis der Division, bis das Ergebnis der Division 0 ist
5. Hinter dem Komma
   1. Multipliziere `n2` mit `b`
   2. Notiere die Zahl **vor** dem Komma und setze sie auf 0
   3. Wiederhole, bis es keine Nachkommastelle mehr gibt


*Beispiel*: 4,625 von Dezimaldarstellung zu Binärdarstellung

`b = 2`

`n1 = 4`

`4 / 2` = `2` Rest `0`

`2 / 2` = `1` Rest `0`

`1 / 2` = `0` Rest `1` ⬅️ Ergebnis der Division ist 0, also aufhören

Reste von unten nach oben: `100`

`n2 = 0.625`

`n2 * 2 = 1.25` 1 vor dem Komma behalten

`0.25 * 2 = 0.5` 0 vor dem Komma behalten

`0.5 * 2 = 1.0` 1 vor dem Komma behalten

Vor-Komma-Zahlen von oben nach unten: `101`

Ergebnis: `4,625` im Dezimalsystem entspricht `100,101` im Binärsystem

# Diskrete Exponentialfunktion

Zum ausrechnen großer Potenzen in Modulo
1. Zerlege den Exponenten in 2er Potenzen (stelle ihn Binär dar)
2. Verdopple den Exponenten ab bis alle benötigten Bestandteile berechnet sind
3. Setze die Besandteile zusammen (nach dem Motto `a^(b + c)` = `a^b * a^c`)

*Beispiel*: Berechne `5^19 mod 11`

**Schritt 1**

`19` binär ist `10011` ⬅️ 5 Stellig, also Exponenten im nächsten Schritt 5 mal (also bis 16) verdoppeln

**Schritt 2**

`5^1 mod 11` = `5`                      

`5^2 mod 11` = `25 mod 11` = `3`

`5^4 mod 11` = `3^2 mod 11` = `9`

`5^8 mod 11` = `9^2 mod 11` = `81 mod 11` = `4`

`5^16 mod 11` = `4^2 mod 11` = `5`

**Schritt 3**

`5^1 mod 11` * `5^2 mod 11` * `5^16 mod 11` = `5 * 3 * 5` = `75 mod 11`

= **`9`**

# Primzahlen

Primzahlen < 100: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97

Primzahlen sind sowas wie Atome.

Eine Zahl die keine Primzahl ist, ist eine zusammengesetzte Zahl, da sie auf eindeutige Weise aus Primzahlen zusammengesetzt ist.

Beispiel: `38`

`36 / 2 = 18` ⬅️ 2 merken

`18 / 2 = 9` ⬅️ 2 merken

`9 / 3 = 3` ⬅️ 3 merken

`3 / 3 = 1` ⬅️ 3 merken

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

| `a` | `b` | kgv |
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

Gegeben `a = b * q + r`, dann ist `ggt(a, b) = ggt(b, r)`

=> Jeder Teiler von `a` und `b` ist auch ein Teiler von `b` und `r`

Schritte:
1. Teile durch `a` durch `b`, um `q` und `r` rauszufinden
2. Schreibe es so auf `a = b * q + r`
3. Setze `a2` := `b` und `b2` := `r`
4. Wiederhole, bis `r = 0` ist
5. Das zweitletzte berechnete `r` ist der ggt des ursprünglichen `a` und `b` 

*Beispiel*: `ggt(222, 40)`

`222 = 5 * 40 + 22`

`40 = 1 * 22 + 18`

`22 = 1 * 18 + 4`

`18 = 4 * 4 + 2` ⬅️ ggt

`4 = 2 * 2 + 0`

**`ggt(222, 40) = 2`**

## Erweiterter Euklidischer Algorithmus

Es existieren ganze Zahlen für `s` und `t`, so dass `ggt(a,b) = a * s + b * t`.

`s` und `t` sind Bézous Koeffizienten.

1. Tabelle erstellen
2. `i` für die Indizes
3. Vorbefüllen: `s0 = 1`, `s1 = 0`, `t0 = 0`, `t1 = 1`
4. Euklidischen Algorithmus ausführen, den Quotienten jeweils `k` eintragen
5. `si+1` (also das nächste s) = `si-1 - ki * si`
6. `ti+1` = `ti-1 - ki * ti` 
7. Die letzten `s` und `t` sind die Koeffizienten

*Beispiel*:

`a = 330`, `b = 156`

| i   | a   | b   | s          | t             | k   | Hilfsspalte für Rechnung |
| --- | --- | --- | ---------- | ------------- | --- | ------------------------ |
| 0   | 330 | 156 | 1          | 0             | -   | `330 = 2 * 156 + 18`     |
| 1   | 156 | 18  | 0          | 1             | 2   | `156 = 8 * 18 + 12`      |
| 2   | 18  | 12  | `1-2*0`=1  | `0-1*2`=-2    | 8   | `18 = 1 * 12 + 6`        |
| 3   | 12  | 6   | `0-1*8`=-8 | `1-(-2)*8`=17 | 1   | `12 = 2 * 6 + 0`         |
| 4   | 6   | 0   | 9          | -19           | 2   |                          |


=> `ggt(330, 156)` = `6` = `9 * 330 + (-19) * 156`

# Lineare Kongruenzen

Additive Inverse auszurechnen ist leicht.

Multiplikative Inverse auszurechnen ist schwer, kann aber auch mit dem erweiterten Euklidischen Algorithmus gemacht werden.

Kongruenz: `a ≡ b mod m` z.B. `2 ≡ 4 mod 2`

Lineare Kongruenzgleichungen: Wie Kongruenzen, nur mit einer Unbekannten:

`a * x ≡ b mod m`

Ob es Lösungen gibt und wie viele, hängt davon ab, was `a`, `b` und `m` ist, z.B.:

`3 * x ≡ 2 mod 2` geht für `x` = `-2, 2, 4, ...`

2 bzw. `m` ist eine Primzahl.

Für Primzahlen (hier `2`) gibt es immer ein multiplikatives Inverse, in diesem Beispiel `3^-1`. Ist `m` keine Primzahl, so existiert ein multiplikatives Inverses trotzdem genau dann, wenn `a` und `x` teilerfremd sind.

Für x gibt es also unendlich viele Lösungen, da man so umstellen kann:

`x = 3^-1 * 2 mod 2`

Ist `m` keine Primzahl, dann kann es für `x` Lösungen geben, muss es aber nicht. Beispiel:

`2 * x ≡ 5 mod 6` hat keine Lösung, da es für 2 kein multiplikatives Inverses in `Z6` gibt. 

Man kann das multiplikative Inverse jetzt berechnen, indem man den Bézoutkoeffizienten `s` betrachtet.

Finden eines multiplikativen Inversen:

1. Brute Force
2. [Verschiebealgorithmus](modulo.md)
3. Erweiterter Euklidischer Algorithmus nehmen um Bézouskoeffizient `s` auszurechnen

`x` berechnen in linearer Kongruenzgleichung:

`t` = `ggt(a, m)`

Wenn `t = 1` (teilerfremd), dann gibt es ein eindeutiges mutliplikatives Inverses zwischenn 1 und `m`

Wenn `t > 1` (nicht teilerfremd)
- Wenn `t` nicht `b` teilt dann gibt es keine Lösung
- Wenn `t` `b` teilt, dann gibt es `t` unterschiedliche Lösungen zwischen 1 und `m`

Wenn das multiplikative Inverse gefunden ist, setze ein in

`x ≡ a^-1 * b mod m`

Tada.

## Chinesischer Restsatz (CRT)
Für ein lineares Kongruenzgleichungssystem (also ganz viele `x ≡ a mod m`), bei dem alle `m` zueinander teilfremd sind, existiert ein eindeutiges `x`, welches kleiner als das Produkt aller `m` ist.

Vorgehen:
1. Checken, ob alle `m` teilerfremd zueinander sind
2. `M`= `m1 * m2 * m3 * ...`
3. `M1` = `M / m1` (also `m1` wieder rausdividieren), `M2` = `M / m2`, ...
4. `y1` = `Inverses(M1) mod m1`, `y2 = Inverses(M2) mod m2`, ...
5. `x` = `a1 * y1 * M1 + a2 * y2 * M2 + ...`
6. Falls `x` größer als `M` ist noch `x` = `x mod M`
7. Prüfen, ob `x` für alle Gleichungen stimmt.

*Beispiel*:

`x ≡ 2 mod 3`

`x ≡ 3 mod 5`

`x ≡ 2 mod 7`

3, 5 und 7 sind zueinander teilfremd. ✅

`M` = `3 * 5 * 7` = `105`

`M1` = `105 / 3` = `35`

`M2` = `105 / 5` = `21`

`M3` = `105 / 7` = `15`

`Inverses(M1) mod m1` = `Inverses(35) mod 3` = `Inverses(2) mod 3` = `2`

`Inverses(M2) mod m2` = `Inverses(21) mod 5` = `Inverses(1) mod 5` = `1`

`Inverses(M3) mod m3` = `Inverses(15) mod 7` = `Inverses(1) mod 7` = `1`

`y1` = `2 mod 3` = `2`

`y2` = `1 mod 5` = `1`

`y3` = `1 mod 7` = `1`

`x` = `(2 * 2 * 35 + 3 * 1 * 21 + 2 * 1 * 15) mod M` = `233 mod 105` = `23` 

Anwendung
- Secret Sharing: Jeder kriegt ein Geheimnis, und nur mit allen (oder einer Mindestanzahl) von Geheimnissen, kann man das gemeinsame Geheimnis entschlüsseln.
- Custom Zahlenranges schaffen. Wenn Zahlen sehr groß werden, ist das ein Problem für Hardware (physikalisch auf bestimmte Größe begrenzt). Daher kann man auch deren CRT Repräsentation nehmen (für klug gewählte zueinander teilerfremde `m`, und dann mit deutlich kleineren Zahlen rechnen) 


## Kleiner Satz von Fermat

Sei `p` eine Primzahl.

für alle `a` gilt

`a^p ≡ a mod p`

für alle `a`, die sich nicht durch `p` teilen lassen (also `a` ist kein Vielfaches von `p`) folgt:

`a^p-1 ≡ 1 mod p`

*Beispiel*:

`2^7` ⬅️ 7 ist eine Primzahl

=> `2 mod 7` = `2`

=> `2 mod 6` = `1` (da unterer Satz: 2 hoch Primzahl minus 1 ≡ 1)

Trick 17: Wenn `p` keine Primzahl ist, dann kann man den kleinen Fermat trotzdem nutzen, indem man diese Formel benutzt:

`a^n ≡ a^r mod p`, wobei `r = n mod (p-1)` ist

Vorgehen:
1. Checken, dass `ggt(a, m)` = 1 ist
2. `m' = (m-1)`
3. `p` in `m'` zerlegen, um `r` auszurechnen
4. `a^r mod m` ausrechnen

*Beispiel*:

`7^222 mod 11`

`a = 7`

`m = 11`

`ggt(a, m)` = `ggt(7,11)` = `1` (7 und 11 sind teilerfremd)

`7^(11-1)` = `7^10` = `1 mod 11` (Da `a^(p-1) = 1 mod p`)

`222 = 22 * 10 + 2` (Den Exponenten zerlegen in `m-1`)

`r = 2`

=> `7^222` = `7^2 mod 11` (Da `a^n` = `a^r mod p`)

=> `49 mod 11` = `5 mod 11` 

___
[Vorheriges: Kombinatorik](kombinatorik.md)