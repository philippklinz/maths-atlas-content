# Maths Atlas Content

[Maths Atlas Engine](https://github.com/philippklinz/maths-atlas-engine) liest diesen statischen, deutschsprachigen Geometrie-Bestand. `atlas.json` enthält sechs Einträge, deren Formeln, Beweise und Belegstellen. Die Zeichnung liegt unter `abbildungen/`.

## Einen Eintrag ergänzen

- `id` bleibt dauerhaft gleich. `title`, `kind` und `summary` sind der sichtbare Titel, die Art des Eintrags und seine eigenständig verständliche Aussage.
- In `formula` stehen Textstücke und optional verknüpfte Symbole wie `{"text":"h","ref":"hypotenusenhoehe"}`. `ref` bezeichnet die ID des erklärenden Eintrags.
- `proofs` enthält beliebig viele Beweise mit eigenen IDs und Titeln. Jeder Schritt hat eine stabile `id`, einen `title`, einen Erklärungstext in `body` und optional eine `formula`. `uses` nennt die IDs der genau hier verwendeten Hilfssätze oder Begriffe.
- Die Engine bildet Rückverweise aus diesen Angaben. Ändert sich die Reihenfolge der Schritte, bleibt der Link über die Schritt-ID gültig. IDs bestehen aus Kleinbuchstaben, Ziffern und Bindestrichen.
- `figure` verweist auf einen Eintrag in `figures`. Dessen Bildpfad ist relativ zu `atlas.json`. Alternativtext und Bildunterschrift gehören zur Abbildung. `notation`, `example` und `sources` können einen Eintrag ergänzen.
- Für ein Anwendungsbeispiel verbindet `links: [{"to":"aehnlichkeitslemma","relation":"example"}]` das Beispiel mit seinem Gegenstand.

## Navigationsprobe

`navigationsprobe.json` ergänzt auf Wunsch 30 kurze Zahlenbeispiele zum Ähnlichkeitslemma. Die Engine lädt sie mit `?probe=30`. Ohne diesen Parameter gehören nur die sechs redaktionellen Einträge zum Verzeichnis.
