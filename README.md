# PARUFYX Goal (PFXG)

Experimenteller Smart Contract für einen Fan-Token mit linearer Bonding
Curve und On-Chain-Profil (Username + Lieblingsverein).

> **Wichtige Hinweise**
> - Dies ist weder Anlageberatung noch ein Angebot oder eine Aufforderung
>   zum Kauf. Der Code wird "wie besehen" bereitgestellt.
> - Der Token vermittelt keine Gewinn-, Umsatz-, Stimm- oder sonstigen
>   Rechte gegenüber dem Entwickler oder Dritten.
> - Der Preis folgt ausschließlich der Kurvenformel. Es gibt keine
>   Rendite-, Rückkauf- oder Wertzusage. Ein Verkauf kann unter dem
>   Kaufpreis liegen (Kurve und 1 % Verkaufsgebühr). Totalverlust möglich.
> - Der Contract ist nicht von Dritten geprüft (kein Audit). Smart-Contract-
>   Fehler können zum Verlust des eingesetzten Geldes führen.
> - Keine Verbindung zu Vereinen, Ligen oder Spielern. Namen und Logos
>   gehören ihren jeweiligen Inhabern.
> - Die Nutzung kann in deinem Land eingeschränkt oder verboten sein.
>   Prüfe Recht und Steuern selbst.

## Funktionen

| Funktion | Beschreibung |
|---|---|
| `buy(amount)` | Kauft `amount` Token. `msg.value` ist die Preisobergrenze, Überschuss wird erstattet |
| `sell(amount, minPayout)` | Verkauft Token, schlägt unter `minPayout` fehl |
| `costFor(amount)` | Kosten eines Kaufs in Wei |
| `payoutFor(amount)` | Auszahlung und Gebühr eines Verkaufs in Wei |
| `currentPrice()` | Aktueller Preis pro Token in Wei |
| `sold()` | Verkaufte Menge |
| `setProfile(username, favoriteClub)` | Eigenes Profil (max. 32 / 48 Bytes) |

## Preismodell

price(s) = basePrice + slope * s / 1e18

`basePrice` und `slope` sind unveränderlich. Es gibt keinen Owner und
keine Admin-Funktionen. Die Verkaufsgebühr (1 %) bleibt in der Reserve.

## Technik

Solidity `^0.8.24`, OpenZeppelin v5. Konstruktor:
`initialBasePrice`, `initialSlope` (Wei, `slope` max. 1e18).

## Status

Entwurf. Nicht auditiert, nicht auf einem öffentlichen Netz deployt.

## Lizenz

MIT (Code). Die Lizenz ersetzt keine rechtliche Prüfung.
