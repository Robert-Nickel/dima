# Zählen

## Summenregel

*Beispiel:* Jemand kann sich ein Projekt aus drei Listen anbieten. Die erste Liste hat 3 Einträge, die zweite hat 5 Einträge und die dritte hat 9 Einträge. Keines der Projekte kommt in mehreren Listen vor.

Die Person kann sich also zwischen 3 + 5 + 9 = 17 Projekten entscheiden.

Definition:

`|A1 ∪ A2 ∪ . . . ∪ Ak|` = `|A1| + |A2| + ... + |Ak|`  

|A| = Anzahl der Elemente der Menge A
∪ = Vereinigung, also ODER
*Das funktioniert nur für disjunkte Mengen, also dürfen sich keine Elemente doppeln*

## Produktregel

*Beispiel:* Es gibt 3 unterschiedliche Routen von Konstanz nach München und 4 unterschiedliche Routen von München nach Wien.

Also gibt es 3 * 4 = 12 unterschiedliche Routen von Konstanz über München nach Wien.

Definition:

`|A1 × A2 × ... × Ak|` = `|A1| * |A2| * ... * |Ak|`  
In anderen Worten: Die Anzahl der kombinierten Möglichkeiten ist das Produkt der Möglichkeitengruppen.

*Beispiel:* Eine Telefonnummer besteht aus diesem Muster:  
`NYX-NNX-XXXX` mit `N ∈ {2 .. 9}`, `X ∈ {0 .. 9}`, `Y ∈ {0, 1}`  

Wie viele unterschiedliche Telefonummern kann es geben?

*Lösung:*  
`|N| = 8`, `|X| = 10`, `|Y| = 2`

`|N| * |Y| * |X| * |N| * |N| * |X| * |X| * |X| * |X| * |X|`

= `8 * 2 * 10 * 8 * 8 * 10 * 10 * 10 * 10 * 10`

= __`1_024_000_000`__

## Das Einschluss-Ausschluss Prinzip
*Beispiel:* In einer Stadt mit 1000 Einwohnern sprechen 90% Deutsch und 50% Englisch.
Also sprechen 400 Einwohner beide Sprachen, da

`90% von 1000 = 900`

`50% von 1000 = 500`

`900 + 500 - 1000 = 400`

Definition für 2 Mengen:

`|A1 ∪ A2|` = `|A1| + |A2| - |A1 ∩ A2|`

Also in anderen Worten: Die Größe der Vereinigung von 2 Mengen ist die Summe der Größen der beiden Mengen minus die Größe der Schnittmenge der beiden Mengen.

![](bilder/inklusion-exklusion.png)


Definition für 3 Mengen:

`|A1 ∪ A2 ∪ A3|`  
= `|A1| + |A2| + |A3| - |A1 ∩ A2| - |A1 ∩ A3| - |A2 ∩ A3| + |A1 ∩ A2 ∩ A3|`

In anderen Worten: Alle zusammenrechnen, die 2-er Schnittmengen abziehen und die Gesamtvereinigung drauf rechnen.
*Das gibt es auch für mehr Mengen, ist aber schwieriger darzustellen.*

Das Einschluss-Ausschluss Prinzip ist eine Verallgemeinerung der Summenregel.

# Taubenschlagprinzip

Wenn es mehr Tauben als Taubenschläge gibt, dann gibt es mindestens einen Taubenschlag, in dem mindestens zwei Tauben sitzen.

Wie viele Tauben sitzen mindestens in einem Taubenschlag? = Aufrunden(`Anzahl der Tauben / Anzahl des Boxen`)

## Ramsey Theorem

*Beispiel:* Auf einer Feier mit 6 Gästen ist jeder Gast mit jedem anderen Gast entweder befreundet oder verfeindet. Dann sind immer mindestens 3 Leute (paarweise) miteinander befreundet oder verfeindet, denn
aus der Sicht einer bestimmten Person hat man entweder mindestens 3 Freunde oder 3 Feinde auf der Party. (Nach Taubenschlag: 5 Personen die in 2 Kategorien gehören können).

Im Fall von mindestens 3 Freunden gilt, dass
- wenn mindestens 2 von ihnen untereinander auch Freunde sind, dann gibt es bereits 3 Leute, die paarweise miteinander befreundet sind.
- wenn keine 2 von ihnen untereinander befreundet sind, dann existiert ebenfalls eine Menge von 3 Leuten, die miteinander (paarweise) verfeindet sind.

Im Fall von mindestens 3 Feinden funktioniert der Beweis analog.


Ramsey Zahlen sind eine Verallgemeinerung des Beispiels, welches eine Mindestanzahl von Leuten definiert,

damit mindestens `m` Leute miteinander befreundet und `n` Leute verfeindet sind.
Hier: R(3,3) = 6

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

=> `P(n,k)` = `n! / (n - k)!`

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
*Beispiel:* Ein Eisverkäufer bietet Eisbecher mit 3 unterschiedlichen Kugeln aus 40 unterschiedlichen Sorten darin an. Wie viele unterschiedliche Eisbecher gibt es, wenn die Reihenfolge der Kugeln egal ist?

Würde die Reihenfolge eine Rolle spielen, so wären es `40! / (40 - 3)!` = `59_280` Permutationen.

Da sie das nicht tut, wurde jede Kombination `3!` = `6` mal zu häufig gezählt, also gibt es `59_280 / 3!` = `9880` unterschiedliche Kombinationen. 

Definition: Wenn es um eine ungeordnete Untermenge mit Größe k von einer Menge der Größe n geht, ist es eine k-Kombination (aus n Elementen).

`C(n, k)` = `P(n,k) / k!`

=> `C(n, k)` = `n! / (k! * (n - k)!)`

## Binomialkoeffizient
![](bilder/binomialkoeffizient.png)

Man sagt: n über k

*Beispiel:* Von 10 Äpfeln haben 3 einen Wurm. Du nimmst 5 für den Apfelkuchen. Wie viele Möglichkeiten gibt es, genau 2 Äpfel mit Wurm in deinem Kuchen zu haben.

Lösung:

A = Anzahl der Möglichkeiten für 2 der 3 (aus 10) Äpfel mit Wurm = `C(3,2)`

B = Anzahl der Möglichkeiten für 3 der 7 (aus 10) Äpfel ohne Wurm = `C(7,3)`

`A * B`

= `C(3,2)` * `C(7,3)` (Produktregel!)

= `105`

## Permutationen mit Zurücklegen
*Beispiel:* In einer zufällig abgespielten Playlist sind 10 Lieder, welche auch mehrfach vorkommen dürfen. Daher gibt es für die ersten fünf Lieder `10 * 10 * 10 * 10 * 10` = `100_000` unterschiedliche Möglichkeiten.

Ein geordneter Satz von k Objekten aus einer Menge der Größe n nennt man k-Permutation mit Zurücklegen.

Anzahl der k-Permuationen mit Zurücklegen: `P(n,k) = n^k`

Es darf `k > n` sein.

## Kombinationen mit Zurücklegen
*Beispiel:* Man würfelt mit zwei Würfeln. Die höhere Zahl (bei Pasch eine beliebige Zahl) stellt den "Zehner" und die kleinere Zahl den "Einer", z.B. 5 und 4 wird zu 54, 6 und 6 zu 66. Wie viele unterschiedliche Werte können auftauchen?

P mit R(6,2) würde 36 ergeben, allerdings sind dann manche Werte mehrfach vorhanden (da eine Permutationen unterschiedliche Reihenfolgen zählt, was hier egal ist.)

Von Hand:
- Ist ein Würfel eine 1, gibt es 6 Möglichkeiten für den anderen.
- Ist ein Würfel eine 2, gibt es 5 Möglichkeiten für den anderen, denn 1|2 wurde schon im ersten Fall abgebildet.
- ...

=> `6 * 5 * 4 * 3 * 2 * 1 = 21`

Eine ungeordnete Auswahl von k Elementen aus einer Menge der Größe n, nennt man k-Kombination mit Zurücklegen.

Anzahl der k-Kombinationen mit Zurücklegen: `C(n,k)` 

= `n + k - 1 über k`

= `(n + k - 1)! / (k! * (n - 1)!)`

*Beispiel:* Gummibärchentüte mit 5 unterschiedlichen Gummibärchen, aus der 5 Gummibärchen gezogen werden.

= `n = 5, k = 5`

= `(5 + 5 - 1)! / 5! * (5 - 1)!`

= `9! / 5! * 4!`

= `362880 / (120 * 24)`

= `126`

## Entscheidungsbaum für Kombinationen und Permutationen
Werden alle Elemente angeordnet?

- Nein
  - Ist die Reihenfolge wichtig?
    - Ja - Variation
      - Mit Zurücklegen?
        - Ja - `n^k`
        - Nein - `n! / (n - k)!`
    - Nein - Kombination
      - Mit Zurücklegen?
        - Ja - `(n + k - 1) über k`
        - Nein - `n über k`
- Ja
  - Mit Zurücklegen?
    - Ja - `n!`
    - Nein - `n! / (l1! * l2! * ... * lk!)`

___
[Vorheriges: Logik](logik.md) | [Nächstes: Zahlentheorie](zahlentheorie.md)