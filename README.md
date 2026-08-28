# Schaltpläne für BBS Projekt (Hilfe sie wissen nicht wohin mit uns)

## Grundvoraussetzugen:
1. Oszillatormodul
2. Waveformgenerator für Sinus/Rechteck/Dreieck/Sägezahn?
3. Lautspechermodul

## Verfügbare Komponenten:
    ICs:
    - NE555
    - LM324
    - LM393
    - UA741
    - ULN2803
    - LM358
    - LM386
    - NE5532
    - ULN2003
    - PC817

## Generell:
-Für jeden Klinkeneingang ein Impedanzwandler? Wegen der Last
-Sinussignal überhaupt erzeugen? Kommt im Analogen eigentlich kaum vor weil unnötig kompliziert
 Könnte später bei Filtern etc. interessant sein
-Aufteilung per https://www.roland.com/uk/blog/get-started-modular-synthesis/
    - Source Module: Erzeugung von Rechteck-, Dreieck- und Sägezahnspannungen
    - Processor Module: Anpassung für Frequenzen etc. 
-CV: Control Voltage, mal gucken wie genau das noch geht ("Invisible Hands" anstatt Potis, kann auch von der Source kommen)
https://www.youtube.com/playlist?list=PLHeL0JWdJLvTuGCyC3qvx0RM39YvopVQN


## Weiteres:
-Oszillator / VCO: 
    Der 555 läuft per Astable Operation, wo dann der duty cycle mit R_A und R_B kontrolliert wird (siehe Datasheet).
    Formeln für Duty Cycle:
    t_H = 0,693 x (R_A + R_B) x C
    t_L = 0,63 x R_B x C
    Festgelegte Zielfrequenzen: ca. 50Hz bis 1kHz erst mal? Demnach t_H = 20...500ms, t_L = 20...500ms 
    Sonst als Taktgeber das gleiche nur mit Frequenzen von 1Hz bis ca 16Hz? (Für Seqeuencer)

-Waveformgenerator:
Erzeugung des Dreiecksignals per Integrator
(?)Erzeugung eines Sägezahnsignals auch per Integrator

-Lautsprecher / VCA:
    Votlage Controlled Amplifier

- Stromversorgung
    Allgemeine 5V nötig, paar Ampere währen nicht schlecht 
    +/- 5V? 12V? Oder sind die Spannungen alle nur im positiven Bereich?