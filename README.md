# README.md
README.md
# PARUFYX Goal (PFXG)

Ein einfacher Fan-Token für den Fußball-Bereich. Fans können Token direkt
gegen BNB/ETH über eine klassische lineare Bonding Curve kaufen und
verkaufen, und jede Adresse kann ein Profil mit Username und
Lieblingsverein hinterlegen.

Kein Investment-Produkt: Es gibt keine Umsatz-, Gewinn- oder
Ausschüttungsbeteiligung und keinen Bezug zu Spieler-Transferrechten. Der
Preis folgt ausschließlich der Bonding-Curve-Formel, nicht einer
zugesicherten Rendite.

## Funktionsübersicht

| Funktion | Beschreibung |
|---|---|
| `buy(amount)` | Kauft `amount` Token gegen BNB/ETH zum aktuellen Kurvenpreis, überzahlte Beträge werden automatisch erstattet |
| `sell(amount)` | Verkauft `amount` Token zurück an den Contract, Auszahlung nach gleicher Kurve |
| `costFor(amount)` | Liefert die Kosten für einen Kauf von `amount` Token, ohne eine Transaktion auszuführen |
| `payoutFor(amount)` | Liefert die Auszahlung für einen Verkauf von `amount` Token, ohne eine Transaktion auszuführen |
| `soldSupply()` | Aktuell im Umlauf befindliche Token-Menge |
| `setProfile(username, favoriteClub)` | Setzt/aktualisiert das eigene Fan-Profil |
| `setCurve(basePrice, slope)` | Nur Owner: passt die Kurvenparameter an |

## Preismodell

Der Preis pro Token folgt einer linearen Bonding Curve:
