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


| [Vorheriges: Ableitungsregeln](ableitungsregeln.md) |      |
| :-------------------------------------------------- | ---: |