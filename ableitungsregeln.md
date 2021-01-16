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

___
[Vorheriges: Prädikatenlogik](praedikatenlogik.md) | [Nächstes: Beweisprinzipien](beweisprinzipien.md)