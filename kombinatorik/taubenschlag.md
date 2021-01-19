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

___
[Vorheriges: Zählen](/kombinatorik/zaehlen.md) | [Nächstes: Permutationen und Kombinationen](/kombinatorik/permutationen-kombinationen.md)