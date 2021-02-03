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
- Wenn `t` `b` teilt, dann gibt es `t` unterschiedliche Lösungen zwischen 1 und `t`

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

`2^7` <- 7 ist eine Primzahl

=> `2 mod 7` = `2`

=> `2 mod 6` = `1` (da unterer Satz: 2 hoch Primzahl minus 1 ≡ 1)

Trick 17: Wenn `p` keine Primzahl ist, dann kann man den kleinen Fermat trotzdem nutzen, indem man diese Formel benutzt:

`a^n ≡ a^r mod p`, wobei `r = n mod (p-1)` ist

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
[Vorheriges: Primzahlen](primzahlen.md) | [Nächstes: Unklar](unklar.md)