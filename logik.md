# Aussagenlogik
## Elementare Aussagen
- Aussagen, die entweder wahr oder falsch sind
- Boolean variables sind elementare Aussagen
- Dinge mit Variablen, Fragen, Wünsche etc. sind keine elementaren Aussagen

## Zusammengesetzte Aussagen
Bestehen aus elementaren Aussagen, die mit logischen Verbindern kombiniert werden.

| Umgangssprache    | Symbol | logischer Name  |
| ----------------- | ------ | --------------- |
| Nicht             | `¬`    | Negation        |
| Und               | `∧`    | Konjunktion     |
| Oder              | `∨`    | Disjunktion     |
| Wenn ... dann     | `→`    | Implikation     |
| Wenn und nur wenn | `↔`    | Äquivalenz      |
| Entweder ... oder | `⊕`    | Exklusives Oder |

Wahrheitstabellen logischer Verbinder  
| `P` | `Q` | `P ∧ Q` | `P ∨ Q` | `P → Q` | `P ↔ Q` | `P ⊕ Q` |
| --- | --- | ------- | ------- | ------- | ------- | ------- |
| F   | F   | F       | F       | T       | T       | F       |
| F   | T   | F       | T       | T       | F       | T       |
| T   | F   | F       | T       | F       | F       | T       |
| T   | T   | T       | T       | T       | T       | F       |

*Beispiel:* Wenn die Beeren am Wegrand reif sind (`r`), dann ist das Wandern nur dann sicher (`w`), wenn keine Bären gesichtet (`¬b`) wurden.
`r → (w ↔ ¬b)`

Wahrheitstabelle für dieses Beispiel:

| `r` | `w` | `b` | `¬b` | `(w ↔ ¬b)` | `r → (w ↔ ¬b)` | Bedeutung                                                                             |
| --- | --- | --- | ---- | ---------- | -------------- | ------------------------------------------------------------------------------------- |
| F   | F   | T   | F    | T          | T              |                                                                                       |
| F   | T   | F   | T    | T          | T              | Aussage wahr und wandern sicher:<br> Wenn Beeren nicht reif und keine Bären gesichtet |
| F   | T   | T   | F    | F          | T              | Aussage wahr und wandern sicher:<br> Wenn Beeren nicht reif und Bären gesichtet       |
| T   | F   | F   | T    | F          | F              |                                                                                       |
| T   | F   | T   | F    | T          | T              |                                                                                       |
| T   | T   | F   | T    | T          | T              | Aussage wahr und wandern sicher:<br> Wenn Beeren reif und keine Bären gesichtet       |
| T   | T   | T   | F    | F          | F              |                                                                                       |

## System Spezifikationen
Konsistenz: Dürfen keine Konflikte oder Widersprüche beinhalten, es muss eine Kombination für die Input Variablen geben, die alle Anforderungen erfüllt.  
*Beispiel:*  
- I. Der Ping muss schneller als 1 Sekunde sein(p) und die Seite in weniger als 2 Sekunden laden(l).
- II. Die Seite lädt nicht in weniger als 2 Sekunden oder der Ping ist nicht schneller als 1 Sekunde.

`I.  p ∧ l`  
`II. ¬l ∨ ¬p`  

Wahrheitstabelle für dieses Beispiel:

| `p` | `l` | `p ∧ l` | `¬l ∨ ¬p` |
| --- | --- | ------- | --------- |
| F   | F   | F       | T         |
| F   | T   | F       | T         |
| T   | F   | F       | T         |
| T   | T   | T       | F         |

Bedeutung: Es gibt keine Zeile, in der beide Anforderungen erfüllt sind. Darum sind diese Spezifikationen inkonsistent.  

## Charakteristiken zusammengesetzter Aussagen
Eigenschaften von zusammengesetzter Aussage P

| Name                       | Eigenschaft                                                                              | Beispiel                    |
| -------------------------- | ---------------------------------------------------------------------------------------- | --------------------------- |
| Tautologie                 | Immer wahr, egal welche Werte die Aussagen haben                                         | `a ∨ ¬a`                    |
| Kontradiktion, Widerspruch | Immer falsch, nicht erfüllbar                                                            | `a ∧ ¬a`                    |
| Erfüllbar                  | Durch mindestens 1 Kombination von Aussagenwerten erfüllt                                | `(a → b) ∧ (b → a)`         |
| Äquivalent zu Q            | Wenn die gleichen Aussagenwerte immer<br>den gleichen Output liefern.<br>Notation: P ≡ Q | `(a → b) ∧ (b → a) ≡ a ↔ b` |

Wenn `P ≡ Q`, dann ist `P ↔ Q` eine Tautologie

## Beweis: De Morgan's law
`¬(P ∧ Q) ≡ ¬P ∨ ¬Q`

Beweis:

| `P` | `Q` | `P ∧ Q` | `¬(P ∧ Q)` | `¬P ∨ ¬Q` |
| --- | --- | ------- | ---------- | --------- |
| F   | F   | F       | T          | T         |
| F   | T   | F       | T          | T         |
| T   | F   | F       | T          | T         |
| T   | T   | T       | F          | F         |

Die letzten 2 Spalten sind gleich, daher ist De Morgan's law wahr.

## Vereinfachen zusammengesetzter Aussagen

| Gesetz              | für  `∨`                          | für `∧`                           |
| ------------------- | --------------------------------- | --------------------------------- |
| Kommutativgesetz    | `P ∨ Q ≡ Q ∨ P`                   | `P ∧ Q ≡ Q ∧ P`                   |
| Assoziativgesetz    | `P ∨ (Q ∨ R) ≡ (P ∨ Q) ∨ R`       | `P ∧ (Q ∧ R) ≡ (P ∧ Q) ∧ R`       |
| Distributivgesetz   | `P ∨ (Q ∧ R) ≡ (P ∨ Q) ∧ (P ∨ R)` | `P ∧ (Q ∨ R) ≡ (P ∧ Q) ∨ (P ∧ R)` |
| Absorptionsgesetz   | `P ∨ (P ∧ Q) ≡ P`                 | `P ∧ (P ∨ Q) ≡ P`                 |
| De Morgans Gesetz   | `¬(P ∨ Q) ≡ ¬P ∧ ¬Q`                | `¬(P ∧ Q) ≡ ¬P ∨ ¬Q`              |
| Doppelnegativgesetz | `¬¬A ≡ A`                         |

# Prädikatenlogik
- Die Aussage, die A(x) über x macht nennt man Prädikat.

*Beispiele:*

| Aussagenfunktion    | Variable | Prädikat    | Wahr für x        | Falsch für x     |
| ------------------- | -------- | ----------- | ----------------- | ---------------- |
| `A(x): x < 100`     | `x`      | `< 100`     | `1`,`99`          | `100`, `999`     |
| `B(x,y): x + y = 0` | `x`,`y`  | `x + y = 0` | `x = 1`, `y = -1` | `x = 1`, `y = 1` |

Aussagefunktionen
- können mit logischen Verbindern kombiniert werden
- hängen mit ihrem Wahrheitsgehalt vom Wert der Variablen ab
- können von mehreren Variablen abhängen
- werden zur Aussage, wenn man
  - die Variable(n) durch feste(n) Wert(e) erstetzt
  - mittels eines Quantors eine Aussage formt

## Quantoren
Universalquantor
- "für alle"
- Notation: `∀x ∈ X : P(x)`
- auch: Allaussage, Allquantor
- Positivbeweis: Alle möglichen Werte prüfen
- Negativbeweis: Ein Gegenbeispiel finden

Existenzquantor
- "es existiert mindestens einer"
- Notation: `∃x ∈ X : P(x)`
- Positivbeweis: Ein Beispiel finden
- Negativbeweis: Alle möglichen Werte prüfen

### Negation quantifizierter Ausdrücke
Das Gegenteil von `Jeder liebt Mathematik`<br>
ist `Es gibt mindestens eine Person, die Mathematik nicht liebt`<br>
(und nicht `Niemand liebt Mathematik`).

De Morgans Gesetz für Quantoren:  
`¬(∀x ∈ X : A(x)) ≡ ∃x∈X : ¬A(x)`  
`¬(∃x∈X : A(x)) ≡ ∀x∈X : ¬A(x)`  

### Verschachtelte Quantoren
Die Reihenfolge von Quantoren kann nicht einfach vertauscht werden!  
*Beispiel:*  
`Q(x, y, z) : x + y = z`
dann gibt es einen Unterschied zwischen  
`∀x ∀y ∃z Q(x, y, z)` => Für alle Kombinationen aus `x` und `y` existiert ein `z`, welches die Summe der beiden ist
und  
`∃z ∀x ∀y Q(x, y, z)` => Es existiert ein `z`, welches die Summe aus allen denkbaren `x` und `y` bildet.


### Negation verschachtelter Quantoren
Nutze De Morgans Gesetz und gehe von links nach rechts, bis du das Prädikat erreichst.  

### Logik höherer Ordnung
- Wenn Prädikate Prädikate haben können.
- Beispiel: *Higher order functions* in Scala (Funktionen als Parameter für Funktionen)

# Ableitungsregeln

*Beispiel:*  
Sherlock Holmes im Rätsel um das gestohlene Rennpferd "Silver Blaze":
- Das Pferd verschwand aus einem Stahl, welcher von einem Wachhund bewacht wurde
- Der Wachhund bellt laut, wenn er einen Fremden sieht
- Der Wachhund bellte nicht laut  
=> Also kannte der Wachhund den Dieb  

*Beispiel:*  
Sokrates ist ein Mensch.  
Wenn Sokrates ein Mensch ist, dann ist Sokrates sterblich.  
∴ Sokrates ist sterblich

## Definitionen
- Ein **Argument** ist eine Sequenz von Aussagen 
- ∴ bedeutet **deshalb**
- Eine **Schlussfolgerung** ist eine Sequenz von zusammengesetzten Aussagen, die in einer Konklusion münden
- Eine Schlussfolgerung ist valide, wenn (und nur wenn) ihre Aussagen wahr sind und auch die Konklusion wahr machen. *In anderen Worten: Die Wahrheit einer Konklusion folgt unausweichlich aus der Wahrheit der Prämissen. Es ist unmöglich, eine valide Schlussfolgerung mit wahren Prämissen zu haben, deren Konklusion falsch ist.*

## Schlussfolgerung validieren
Zwei Wege:
1. Nutze eine Wahrheitstabelle und zeige, dass wenn alle Prämissen wahr sind, die Konklusion auch wahr ist. *Problem:* Dauert lange (`2^n` Zeilen)
2. Kombiniere einfache Schlussfolgerungen. *Problem:* Schwierig zu beweisen, dass eine Schlussfolgerung falsch ist.

### Modus Ponens

`p → q`  
`p`  
∴ `q`

*Beispiel:* Wenn du ein Passwort hast, dann kannst du dich einloggen. Du hast ein Passwort. Also kannst du dich einloggen.  

Wahrheitstabelle zur Validierung des Modus Ponens:

| `p` | `q` | `p → q` |                                                                              |
| --- | --- | ------- | ---------------------------------------------------------------------------- |
| F   | F   | T       |                                                                              |
| F   | T   | T       |                                                                              |
| T   | F   | F       |                                                                              |
| T   | T   | T       | Die Prämissen `p → q` und `p` sind wahr,<br>die Konklusion `q` ist auch wahr |

### Komplizierteres Beispiel

`p → q ∨ ¬r`  
`q → p ∧ r`  
∴ `p → r`  

Wahrheitstabelle dazu:

| `p` | `q` | `r` | `q ∨ ¬r` | `p ∧ r` | `p → q ∨ ¬r` | `q → p ∧ r` | `p → r` |                                                                                 |
| --- | --- | --- | -------- | ------- | ------------ | ----------- | ------- | ------------------------------------------------------------------------------- |
| F   | F   | F   | T        | F       | T            | T           | T       |                                                                                 |
| F   | F   | T   | F        | F       | T            | T           | T       |                                                                                 |
| F   | T   | F   | T        | F       | T            | F           | T       |                                                                                 |
| F   | T   | T   | T        | F       | T            | F           | T       |                                                                                 |
| T   | F   | F   | T        | F       | T            | T           | F       | Prämissen sind wahr, Konklusion ist falsch.<br> Daher invalide Schlussfolgerung |
| T   | F   | T   | F        | T       | F            | T           | T       |                                                                                 |
| T   | T   | F   | T        | F       | T            | F           | F       |                                                                                 |
| T   | T   | T   | T        | T       | T            | T           | T       |                                                                                 |

### Modus tollens

`¬q`  
`p → q`  
∴ `¬p`

*Beispiel:* Wenn du kein Passwort hast, und du ein Passwort brauchst, um dich einzuloggen, dann kannst du dich nicht einloggen.

### Ableitungsregeln für Aussagenlogik

| Ableitungsregel                  | Tautologie                       | Name                       | Beispiel                                                                                                                                                           |
| -------------------------------- | -------------------------------- | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `p → q`<br>`p`<br>∴ `q`          | `(p ∧ (p → q)) → q`              | Modus Ponens               | Wenn du ein Passwort hast,<br> dann kannst du dich einloggen.<br> Du hast ein Passwort.<br> Also kannst du dich einloggen.                                         |
| `¬q`<br>`p → q`<br>∴ `¬p`        | `(¬q ∧ (p → q)) → ¬p`            | Modus Tollens              | Wenn du kein Passwort hast,<br> und du ein Passwort brauchst, um dich einzuloggen,<br> dann kannst du dich nicht einloggen.                                        |
| `p → q`<br>`q → r`<br>∴ `p → r`  | `((p → q) ∧ (q → r)) → (p → r)`  | Hypotethischer Syllogismus | Wenn die Sonne scheint, grillen wir.<br> Wenn wir grillen, werden wir satt.<br> Die Sonne scheint.<br> Daher werden wir Satt, wenn die Sonne scheint.              |
| `p ∨ q`<br>`¬q`<br>∴ `q`         | `((p ∨ q) ∧ ¬p) → q`             | Disjunktive Syllogismus    | Wenn einer von uns beiden gekocht hat,<br> und ich habe nicht gekocht,<br> dann hast du gekocht.                                                                   |
| `p`<br>∴ `p ∨ q`                 | `p → (p ∨ q)`                    | Addition                   | Es friert.<br> Daher friert es, oder es regnet.                                                                                                                    |
| `p ∧ q`<br>∴ `p`                 | `(p ∧ q) → p`                    | Vereinfachung              | Es friert und regnet.<br> Daher friert es.                                                                                                                         |
| `p`<br>`q`<br>∴ `p ∧ q`          | `((p) ∧ (q)) → (p ∧ q)`          | Konjunktion                | Es friert. Es regnet. Also friert und regnet es.                                                                                                                   |
| `p ∨ q`<br>`¬q ∨ r`<br>∴ `q ∨ r` | `((p ∨ q) ∧ (¬q ∨ r)) → (p ∨ r)` | Auflösung                  | Es ist schlecht beschrieben<br> oder ich bin dumm.<br> Ich bin nicht dumm<br> oder ich bin sehr dumm. Also ist es schlecht beschrieben<br> oder ich bin sehr dumm. |

### Anwendung des Ableitungsregeln
Für kompliziertere Argumente mit mehreren Prämissen, welche nicht direkt zu den obigen korrespondieren:
1. Nutze eine Ableitungsregel, um eine vorläufige Konklusion aus einer oder mehreren Prämissen (oder schon vorhandenen vorläufigen Konklusionen) abzuleiten.
2. Wiederhole bis eine gewünschte Konklusion erreicht wird.  

*Beispiel:* Prämissen:
1. Es ist sonnig und heiß. `s ∧ h`
2. Wenn es sonnig ist, trage ich eine Sonnenbrille. `s → b`
=> Konklusion: Ich trage eine Sonnenbrille. `b`

`s ∧ h`  
`s → b`  
∴ `b`

Mittels Vereinfachung `s ∧ h` → `s` zu Modus Ponens:  
`s`  
`s → b`  
∴ `b`  
*Schlussfolgerung:* Das Argument ist valide. Ich trage einen Sonnenbrille. 😎  

### Ableitungsregeln für quantifizierte Ausdrücke

| Name                          | Ableitungsregel                        | Erklärung                                                                                                                      |
| ----------------------------- | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Universelle Instanziierung    | `∀x P(x)`<br>∴ `P(c)`                  | Wenn eine Eigenschaft für<br> alle Werte einer Gruppe wahr ist,<br> dann ist jeder konkrete Wert dieser Gruppe wahr.           |
| Universelle Generalisierung   | `P(c)` für beliebiges c<br>∴ `∀x P(x)` | Wenn eine Eigenschaft für<br> einen beliebigen Wert einer Gruppe wahr ist,<br> dann ist sie für alle Werte wahr.               |
| Existenziellle Instanziierung | `∃x P(x)`<br>∴ `P(c)` für ein c        | Wenn ein Wert existiert,<br> für den eine Eigenschaft wahr ist,<br> dann ist diese Eigenschaft für einen bestimmten Wert wahr. |
| Existenzielle Generalisierung | `P(c)` für ein c<br>∴ `∃x P(x)`        | Wenn eine Eigenschaft für<br> einen bestimmten Wert wahr ist,<br> dann existiert ein Wert, für den diese Eigenschaft wahr ist. |

*Beispiel:* `Jeder im Kurs hat einen Bachelor` und `Robert ist im Kurs`  
Nutzung der universellen Instanziierung: `Robert hat einen Bachelor`  

## Ableitungsmaschinen (Inference Engines)
Ableitungsmaschinen ermöglichen:
- **Forward Chaining**: Deduktion neuer Information aus Wissensdatenbank 
- **Backward Chaining**: Beweise finden durch Etablierung valider Ketten und Auffinden notwendiger Prämissen in der Wissensdatenbank 
[Mehr darüber hier.](http://aima.eecs.berkeley.edu/slides-pdf/chapter09.pdf)

# Beweisprinzipien

## Terminologie
- Satz/Theorem: Ein Ausdruck, der als wichtig erachtet wird und bewiesen werden kann. Beispiel: Satz des Pythagoras.
- Axiom: Ein Ausdruck, der für wahr gehalten wird.
- Beweis: Ein valides Argument das die Wahrheit eines Satzes belegt. Besteht aus:
  - Axiomen (den Prämissen des Satzes)
  - Bereits bewiesenen Sätzen
  - Ableitungsregeln, welche die Konklusion des Satzes daraus herleiten
- Lemma: Wenig wichtiger Satz, der als Baustein eines wichtigeren Satzes fungiert.
- Korollar: Ein Satz, der direkt von einem anderen Satz, welcher bewiesen wurde, abgeleitet werden kann.
- Vermutung: Ein Ausdruck, der als wahr vermutet wird, aber noch nicht bewiesen werden konnte. Wird eine Vermutung bewiesen, so wird ein Satz daraus.  

## Beweismethoden
- Direkter Beweis: Beweist einen Satz `p → q` durch die Annahme, das `p` wahr ist, und durch Zeigen, dass `q` dann auch wahr sein muss.
- Indirekter Beweis/Kontraposition: Beweist einen Satz `p → q` durch Zeigen, dass `¬q → ¬p` wahr ist (mittels direktem Beweis).
- Widerspruchsbeweis/Kontradiktion: Beweist das `p` wahr ist, indem man `¬p` annimmt, und dann einen logischen Widerspruch erzeugt. "Reductio ad absurdum"
- Induktionsbeweis: Beweist das `P(n)` für alle `n` wahr ist, indem man `P(0)` beweist und dann zeigt, dass `P(k) → P(k + 1)` für beliebiges `k` auch wahr ist. `n` ist ein Teil einer rekursiv definierten Gruppe, z.B. der natürlichen Zahlen.
- [...weitere Methoden](https://en.wikipedia.org/wiki/Mathematical_proof)  

## Beispiel: direkter Beweis
Wenn `n` eine ungerade Zahl ist, dann ist `n^2` ungerade.  Direkter Beweis:  
1. Übersetze `n ist ungerade` zu `n = 2k +1` für `k ∈ Z`
2. `n = 2k +1` ist wahr
3. `n^2 = (2k +1)^2` wird zu
4. `n^2 = 4k^2 + 4k + 1` mittels 1. bin. Formel
5. Ersetze `2k^2 + 2k` mit `m`
6. `n^2 = 2m + 1`
7. und das bedeutet, `n^2` ist auch ungerade

___
[Nächstes: Kombinatorik](kombinatorik.md)