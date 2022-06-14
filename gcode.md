# Gcode standaard

Dit document bevat de gcode standaard met uitleg wat welk commando betekend.
De volgorde van de gcode is vast en de volgorde van de parameters kan dus niet gewisseld worden ondanks dat er een indentificatieletter voor elk parameter staat.

## Tekenen

### G0: Opgetild verplaatsen

___
G0 wordt gebruikt voor het verplaatsen van de pen terwijl de pen van het papier getild is.

Het G0 commando heeft 2 paramaters

- X: Het x-coordinaat van het speelbord waar de pen naar toe moet bewegen
- Y: Het y-coordinaat van het speelbord waar de pen naar toe moet bewegen

Om de pen te verplaatsen naar (1000, 1000) zonder een lijn te tekenen:
``G0 X1000 1000``


### G1: Tekenend verplaatsen

___
G1 wordt gebruikt voor het verplaatsen van de pen terwijl de pen op het papier staat.

Het G1 commando heeft 2 paramaters

- X: Het x-coordinaat van het speelbord waar de pen naar toe moet bewegen
- Y: Het y-coordinaat van het speelbord waar de pen naar toe moet bewegen

Om de pen te verplaatsen naar (1000, 1000) terwijl een lijn te tekenen:
``G1 X1000 1000``

### G28: Home

___
G28 wordt gebruikt voor het teruggaan naar home na het tekenen.
Het G28 commando heeft geen paramaters en wordt dus aangeroepen door het commando.
``G28`

## Zeeslag

### G3: Tekenen zeeslag bord

___
G3 wordt gebruikt voor tekenen van het eigen bord en het bord van de tegenstander

Het G3 commando heeft geen paramaters en wordt dus aangeroepen door het commando.
``G3``

### G4: Hit

___
G4 wordt gebruikt voor tekenen van een hit.

Het G4 commando heeft 3 paramaters

- R: De row van het speelbord waar de hit is
- C: De colom van het speelbord waar de hit is
- P: Indicatie of het bij de eigen speler is of bij de vijand
    - 0: geeft aan op het bord van de eigen speler
    - 1: geeft aan op het bord van de vijand

Om een hit te tekenen in A1 op het eigen bord wordt dus gebruikt:
``G4 R1 C1 P0``

### G5: Miss

___
G5 wordt gebruikt voor tekenen van een miss.

Het G5 commando heeft 3 paramaters

- R: De row van het speelbord waar de miss is
- C: De colom van het speelbord waar de miss is
- P: Indicatie of het bij de eigen speler is of bij de vijand
    - 0: geeft aan op het bord van de eigen speler
    - 1: geeft aan op het bord van de vijand

Om een miss te tekenen in A1 op het eigen bord wordt dus gebruikt:
``G5 R1 C1 P0``

### G6: Boats

___
G6 wordt gebruikt voor tekenen van de boten.

Het G6 commando heeft 4 paramaters

- R: De row van het speelbord waar het begin van de boot is
- C: De colom van het speelbord waar het begin van de boot is
- W: De width van de boot
- L: De length van de boot

*Let op: als de width en length beide ongelijk zijn aan 1 dan wordt de boot niet getekend omdat dat in overtreding van de standaard is.*

Om een boat van 2 lang te tekenen in vakje A1 gebruik je: 
``G5 R1 C1 W1 L2``
