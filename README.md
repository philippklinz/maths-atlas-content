# Maths Atlas Content

[Maths Atlas](https://philipp-klinz.net/maths-atlas-engine/) erschließt die deutschsprachigen Einträge aus `atlas.json`. Die [Engine](https://github.com/philippklinz/maths-atlas-engine) bildet die beiden Richtungen eines fachlichen Verweises ab. Die Zeichnungen liegen unter `abbildungen/`.

| Gebiet | Themen |
| --- | --- |
| Algebra | Terme und Wurzeln · Verhältnisse und Gleichungen |
| Arithmetik | Brüche und Anteile · Zahlen und Konstanten |
| Geometrie | Kreis und Winkel · Längen und Flächen · Rechtwinklige Dreiecke · Zylinder |

## Einen Eintrag ergänzen

- `id` bleibt dauerhaft gleich. `title`, `kind` und `summary` sind der sichtbare Titel, die Art des Eintrags und seine eigenständig verständliche Aussage.
- `areas` beschreibt die Gebiete mit ihren `topics`. Jedes Gebiet und Thema hat eine stabile ID, einen Titel und einen kurzen Überblick. Themen-IDs sind atlasweit eindeutig. Jeder Eintrag nennt seine Themen-ID in `topic`. Daraus entstehen Startseite, Verzeichnis und Themenfilter. Fachliche Verknüpfungen können in andere Gebiete führen.
- In `formula` stehen Textstücke und optional verknüpfte Symbole wie `{"text":"h","ref":"hypotenusenhoehe"}`. `ref` bezeichnet die ID des erklärenden Eintrags.
- `proofs` enthält beliebig viele Beweise mit eigenen IDs und Titeln. Jeder Schritt hat eine stabile `id`, einen `title`, einen Erklärungstext in `body` und optional eine `formula`. `uses` nennt die IDs der genau hier verwendeten Hilfssätze oder Begriffe.
- Die Engine bildet Rückverweise aus diesen Angaben. Ändert sich die Reihenfolge der Schritte, bleibt der Link über die Schritt-ID gültig. IDs bestehen aus Kleinbuchstaben, Ziffern und Bindestrichen.
- `figure` verweist auf einen Eintrag in `figures`. Dessen Bildpfad ist relativ zu `atlas.json`. Alternativtext und Bildunterschrift gehören zur Abbildung. `notation`, `example` und `sources` können einen Eintrag ergänzen.
- Für ein Anwendungsbeispiel verbindet `links: [{"to":"aehnlichkeitslemma","relation":"example"}]` das Beispiel mit seinem Gegenstand.

## Navigationsprobe

Wie kommt man von der [Kreiszahl π](https://philipp-klinz.net/maths-atlas-engine/#eintrag=pi) zum Volumen einer Dose? Welche Rechenregel erklärt beim [Kreisring](https://philipp-klinz.net/maths-atlas-engine/#eintrag=kreisring), warum die Ringbreite in der Flächenformel vorkommt? Beide Wege sind Teil des regulären Bestands.

`navigationsprobe.json` ergänzt auf Wunsch 30 zusätzliche Zahlenbeispiele zum Ähnlichkeitslemma. Die Engine lädt sie mit `?probe=30`.
