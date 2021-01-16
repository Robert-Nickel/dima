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
| De Morgans Gesetz   | `¬(P∨ Q) ≡ ¬P ∧ Q`                | `¬(P ∧ Q) ≡ ¬P ∨ ¬Q`              |
| Doppelnegativgesetz | `¬¬A ≡ A`                         |


|      | [Nächstes: Prädikatenlogik](praedikatenlogik.md) |
| :--- | -----------------------------------------------: |