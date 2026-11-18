# Inhaltskarte

Automatisch erzeugt mit `werkstatt/werkzeuge/karte.py`. Stand: c227291, 2026-11-18: Hochzeitskarten 4003 (Stand aus APPs)

Vorgehen: Abschnitt hier finden → `grep -n "<Titel>" index.html` → nur diesen Bereich lesen.

## `index.html` – Hochzeitskarten 4003
1944 Zeilen, 369 KB.

**Datenblöcke – nie komplett ausgeben** (z. B. `cut -c1-200` oder `awk 'length<3000'`):

- Zeile 492: 13 KB – `g: {" ":[189,[]],"!":[158,[[158,331,158,110],[158,32,142,16…`
- Zeile 494: 23 KB – `g: {" ":[189,[]],"!":[158,[[142,331,126,299,142,110,158,299…`
- Zeile 496: 21 KB – `g: {" ":[189,[]],"!":[173,[[176,331,160,315,129,126],[176,3…`
- Zeile 498: 22 KB – `g: {"0":[251,[[123,9,153,16,185,47,199,81,205,118,208,170,2…`
- Zeile 500: 14 KB – `g: {"0":[381,[[65,268,65,30,93,3,342,3,372,32,372,274,347,2…`
- Zeile 502: 19 KB – `g: {"0":[281,[[188,164,174,255,139,310,94,328,49,310,14,255…`
- Zeile 504: 40 KB – `g: {"0":[315,[[189,331,142,315,110,268,95,189,95,142,110,63…`
- Zeile 506: 15 KB – `g: {" ":[12,[]],"!":[7,[[3.5,21,3.5,7],[3.5,2,2.5,1,3.5,0,4…`
- Zeile 508: 21 KB – `g: {" ":[12,[]],"!":[12,[[8.5,21,7.5,20,5.5,8],[8.5,20,5.5,…`
- Zeile 510: 15 KB – `g: {" ":[12,[]],"!":[12,[[8.5,21,7.5,20,5.5,8],[8.5,20,5.5,…`

**Bedien-Bereiche (HTML)**

- 204: `<nav>` Bereiche
- 212: `<section>` panel

**Abschnitte im Code** (Suchbegriff = Titel)

| Zeile | Abschnitt | Funktionen |
|---|---|---|
| 27–40 | Raster |  |
| 40–69 | Bühne |  |
| 69–616 | Bedienfeld |  |
| 616–740 | Geometrie: alles in mm, y nach unten | clamp, bbox, fitTo, rectPts, circlePts, ellipsePts, heartRaw, HEART_RATIO, heartPts, archPts, roundRectPts, diamondPts … +12 |
| 740–758 | Rauschen (Perlin) für Verbiegungen | makeRng, makeNoise |
| 758–784 | Kanten: gerade, Bögen, Wellen, Spitze | edgePath |
| 784–872 | Muster (aus dem In And Out Liner: Moiré und Linienscharen) | family, topoLines, genPattern, patternRegion |
| 872–927 | Schrift im Muster (Maske wie im In And Out Liner) | fontStack, boxBlur, motifMask, maskContours |
| 927–955 | Stift-Schrift (Einstrich-Schriften aus dem Abwickler) | capOf, layoutText, placeText |
| 955–987 | Linienband (aus dem In And Out Liner) | smoothFlat, bandGeom, randomStroke |
| 987–1007 | Masken für ein Blatt: wo der Stift zeichnen darf | rasterMask, polyRaster, pathPoly, textMask |
| 1007–1032 | Formate und Schnitte | newSheet, outlinesOf, closeFlat, flatLen, dedupe |
| 1032–1055 | Panels: Fläche in eigenen Koordinaten (lx, ly) -> Blatt | panelMap, panelPart, mapFlatLines, mapPoly |
| 1055–1121 | kleine Formen (lokale Koordinaten) | halfDisc, quarterDisc, pillPts, triPts, blobPts, leafPts, annulusHalf, segDist, minDist, collides, insideRect, hatchPoly … +1 |
| 1121–1137 | Klappkarte: Grundlage für Ausschnitt, Lamellen, Typo | foldCard, footOf |
| 1137–1196 | AUSSCHNITT: Bauhaus, Blobs, Matisse, Regenbogen | cutoutDesign |
| 1196–1237 | LAMELLEN: parallele Schlitze | slitDesign |
| 1237–1280 | NAHT: Torkarte mit geformter Kante | seamFn, seamPts, seamCard, bandSheet |
| 1280–1339 | HORIZONT: Leporello mit Landschaftskante | horizonProfile, yAt, horizonCard |
| 1339–1400 | SKULPTUR: zwei Steckteile | rasterParts, pathPts, sculptShape, sculptSheet |
| 1400–1445 | TYPO: große Buchstaben als Fenster oder Stiftfläche | textRaster, stencilBridges, dilateMask, typoDesign |
| 1445–1475 | Einleger und Umschlag | insertSheet, envelopeSheet |
| 1475–1508 | Alles zusammen | cardSize, buildCard |
| 1508–1519 | Wo der Stift zeichnen darf | paperMask |
| 1519–1602 | Ein Blatt zusammensetzen: Stiftlinien je Stift | memo, composeSheet |
| 1602–1663 | Zustand | deepFill, dKey, newDesign, mkText, seedDefaults |
| 1663–1684 | Pfad-Zugriff | curSheet, designOf, curDesign, ref, getV, setV, $, testIf, fmtNum, esc |
| 1684–1758 | Bedienelemente füllen | swatch, fillStatic, penSegs, syncControls, fitsWH, autoFormat |
| 1758–1784 | Textliste | renderTextList |
| 1784–1794 | Zeichnen mit dem Finger | drawing, svgPoint, endStroke, drawLive |
| 1794–1851 | Vorschau | f2, dPoly, dFlat, penHex, paperOf, canMock, penPaths, renderPreview, renderMock, shade, thumbFormat, typeThumbs |
| 1851–1892 | Export | sheetSVG, fileName, resultFor, downloadSheet, shareSheet, saveAll, canShare, fits, cm, penMeters, cutMeters, renderSheetList |
| 1892–1900 | Logo: In and Outliner mit der Stiftschrift | logoSVG |
| 1900–1944 | Ablauf | cardCfg, buildCardMemo, buildThumb, changed, render |
