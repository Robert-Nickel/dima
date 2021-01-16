# Ableitungsregeln und Beweisprinzipien

*Beispiel:*  
Sherlock Holmes im Rätsel um das gestohlene Rennpferd "Silver Blaze":
- Das Pferd verschwand aus einem Stahl, welcher von einem Wachhund bewacht wurde
- Der Wachhund bellt laut, wenn er einen Fremden sieht
- Der Wachhund bellte nicht laut  
=> Also kannte der Wachhund den Dieb  

## Ableitungsmaschinen (Inference Engines)
Ableitungsmaschinen ermöglichen:
- **Forward Chaining**: Deduktion neuer Information aus Wissensdatenbank 
- **Backward Chaining**: Beweise finden durch Etablierung valider Ketten und Auffinden notwendiger Prämissen in der Wissensdatenbank 

*Beispiel:*  

Sokrates ist ein Mensch.  
Wenn Sokrates ein Mensch ist, dann ist Sokrates sterblich.
____
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
_______
∴ `q`

*Beispiel:* Wenn du ein Passwort hast, dann kannst du dich einloggen. Du hast ein Passwort. Also kannst du dich einloggen.  

Wahrheitstabelle zur Validierung des Modus Ponens:

| `p` | `q` | `p → q` |                                                                           |
| --- | --- | ------- | ------------------------------------------------------------------------- |
| F   | F   | T       |                                                                           |
| F   | T   | T       |                                                                           |
| T   | F   | F       |                                                                           |
| T   | T   | T       | Die Prämissen `p → q` und `p` sind wahr, die Konklusion `q` ist auch wahr |

### Komplizierteres Beispiel

`p → q ∨ ¬r`  
`q → p ∧ r`
____________
∴ `p → r`  

Wahrheitstabelle dazu:

| `p` | `q` | `r` | `q ∨ ¬r` | `p ∧ r` | `p → q ∨ ¬r` | `q → p ∧ r` | `p → r` |                                                                             |
| --- | --- | --- | -------- | ------- | ------------ | ----------- | ------- | --------------------------------------------------------------------------- |
| F   | F   | F   | T        | F       | T            | T           | T       |                                                                             |
| F   | F   | T   | F        | F       | T            | T           | T       |                                                                             |
| F   | T   | F   | T        | F       | T            | F           | T       |                                                                             |
| F   | T   | T   | T        | F       | T            | F           | T       |                                                                             |
| T   | F   | F   | T        | F       | T            | T           | F       | Prämissen sind wahr, Konklusion ist falsch. Daher invalide Schlussfolgerung |
| T   | F   | T   | F        | T       | F            | T           | T       |                                                                             |
| T   | T   | F   | T        | F       | T            | F           | F       |                                                                             |
| T   | T   | T   | T        | T       | T            | T           | T       |                                                                             |

### Modus tollens

`¬q`  
`p → q`
_______
∴ `¬p`

*Beispiel:* Wenn du kein Passwort hast, und du ein Passwort brauchst, um dich einzuloggen, dann kannst du dich nicht einloggen.

### Ableitungsregeln für Aussagenlogik
+-----------------+---------------------+--------------+
| Ableitungsregel | Tautologie          | Name         |
+=================+=====================+==============+
| `p → q`         | `(p ∧ (p → q)) → q` | Modus Ponens |
| `p`             |                     |              |
| ∴ `q`           |                     |              |
+-----------------+---------------------+--------------+



| x       | y   | z   |
| ------- | --- | --- |
| `¬q`    |     |     |
| `p → q` |     |     |
| ∴ `¬p`  |     |     |