TARGET DECK: DATCOM::Leitungscodes

Leitungscodes: NRZ-L #flashcard
- 1: hoher Pegel, 0: niedriger Pegel
- 100% Effizienz
- *nicht* selbsttaktend
(*Der Standard*)
<!--ID: 1793703995627-->

Leitungscodes: NRZ-M #flashcard
- Pegelwechsel bei 1, keiner bei 0
- differentiell
- 100% Effizienz
- *nicht* selbsttaktend
<!--ID: 1793703995632-->


Leitungscodes: NRZ-S #flashcard
- Pegelwechsel bei 0, keiner bei 1
- differentiell
- 100% Effizienz
- *nicht* selbsttaktend
<!--ID: 1793703995636-->



Leitungscodes: Bi-Phase-L #flashcard
- Wechsel in jeder Bitmitte: 1 fällt, 0 steigt
- 50% Effizienz
- selbsttaktend
(*Manchester*)
<!--ID: 1793703995640-->


Leitungscodes: Bi-Phase-M #flashcard
- Wechsel an jedem Bitanfang, bei 1 zusätzlich in der Mitte
- 50% Effizienz
- selbsttaktend
  
Leitungscodes: Bi-Phase-S #flashcard
- Wechsel an jedem Bitanfang, bei 0 zusätzlich in der Mitte
- 50% Effizienz
- selbsttaktend
<!--ID: 1793703995644-->


DBi-Phase-M
- Wechsel in jeder Bitmitte, bei 0 zusätzlich am Bitanfang
- 50% Effizienz
- selbsttaktend
(*Diff. Manchester**)

DBi-Phase-S
- Wechsel in jeder Bitmitte, bei 1 zusätzlich am Bitanfang
- 50% Effizienz
- selbsttaktend


RZ (Return to Zero)
- 1: positiver 0: negativer pegel in der ersten Bithälfte. Danach Nullpegel
- 50% Effizienz
- selbsttaktend

AMI (Alternating Mark Inversion)
- 0: Nullpegel, 1: Puls über das ganze bit, abwechselnd positiv und negativ
- 100% Effizienz
- nicht selbsttaktend


mod. AMI (Alternating Mark Inversion)
- 1: Nullpegel, 0: Puls über das ganze bit, abwechselnd positiv und negativ
- 100% Effizienz
- nicht selbsttaktend

Was unterscheidet nB/mB Blockcodes und nB/mT Blockcodes von einander? #flashcard
- nB/mB übersetzen nur Bits in Bits: Sie benötigen einen *seperaten Leitungscode* um diese in *Pegelstände* umzusetzen
- nB/mT Codes sind *Blockcode und Leitungscode in einem*
<!--ID: 1793703995648-->


Wie funktioniert der 4B/5B Blockcode? #flashcard
- Übersetze Blöcke von 4 Bit in Blöcke von 5 Bit.
- Wähle die genutzten 5 Bit Blöcke so, dass bei keiner Kombination an Worten mehr als 3 auf einander folgende 0en entstehen
	- nutze übrige 5 Bit Wörter für Steuerzeichen
- Übertrage mit NRZ-M (differentiell mit Wechsel bei 1)
<!--ID: 1793703995652-->


Tabelle: Wann wechseln die Bi-Phase und die DBi-Phase Codes den Pegel? #flashcard

| Code        | Bitanfang     | Bitmitte                                 |
| ----------- | ------------- | ---------------------------------------- |
| Bi-Phase-L  | -             | Immer Wechsel:<br>0 = hoch<br>1 = runter |
| Bi-Phase-M  | Immer Wechsel | Bei 1                                    |
| Bi-Phase-S  | Immer Wechsel | Bei 0                                    |
| DBi-Phase-M | Bei 0         | Immer                                    |
| DBi-Phase-S | Bei 1         | Immer Wechsel                            |
<!--ID: 1793704802541-->

