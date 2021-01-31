# Diskrete Exponentialfunktion

Zum ausrechnen großer Potenzen in Modulo
1. Zerlege den Exponenten in 2er Potenzen (stelle ihn Binär dar)
2. Verdopple den Exponenten ab bis alle benötigten Bestandteile berechnet sind
3. Setze die Besandteile zusammen (nach dem Motto `a^(b + c)` = `a^b * a^c`)

*Beispiel*: Berechne `5^19 mod 11`

**Schritt 1**

`19` binär ist `10011` <- 5 Stellig, also Exponenten im nächsten Schritt 5 mal (also bis 16) verdoppeln

**Schritt 2**

`5^1 mod 11` = `5`                      

`5^2 mod 11` = `25 mod 11` = `3`

`5^4 mod 11` = `3^2 mod 11` = `9`

`5^8 mod 11` = `9^2 mod 11` = `81 mod 11` = `4`

`5^16 mod 11` = `4^2 mod 11` = `5`

**Schritt 3**

`5^1 mod 11` * `5^2 mod 11` * `5^16 mod 11` = `5 * 3 * 5` = `75 mod 11`

= **`9`**


___
[Vorheriges: Zahlenrepräsentation](zahlenrepraesentation.md) | [Nächstes: unklar](unklar.md)