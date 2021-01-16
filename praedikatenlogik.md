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

[Vorheriges: Prädikatenlogik](praedikatenlogik.md) | [Nächstes: Ableitungsregeln](ableitungsregeln.md)