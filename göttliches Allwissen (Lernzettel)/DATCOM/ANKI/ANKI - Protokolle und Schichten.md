TARGET DECK: DATCOM::Protokolle und Schichten

Definiere **horizontale vs. vertikale Kommunikation** #flashcard
- Horizontal: "scheinbare" Kommunikation zwischen Instanzen in der gleichen Schicht.
- Vertikal: tatsächliche Kommunikation innerhalb eines Protokollstapels: Tiefer liegende Schichten erbringen den Kommunikationsdienst.
<!--ID: 1793019081197-->


Definiere die Namen der **5 Informationsblöcke** bei der Vertikalen Kommunikation in einem Protokollstapel. #flashcard
- IDU = Interface Data Unit
- ICI = Interface Control Information
- SDU = Service Data Unit
- PCL = Protocol Control Information
- PDU = Protocol Data Unit
<!--ID: 1793019081204-->


Definiere die **IDU, Interface Data Unit** #flashcard
Der Block, der an der Schnittstelle übergeben wird.
<!--ID: 1793019081211-->


Definiere die **ICI = Interface Control Information**
Ist als Teil der IDU **vertikal** als Information für die direkt darüber/darunter liegende Schicht bestimmt.

Definiere die **SDU = Service Data Unit** #flashcard
Der Nutzdatenblock, den man aus der von oben kommenden IDU erhält, nachdem man die ICI entfernt hat. _Man betrachtet den Inhalt der von oben erhaltenen SDU nicht
<!--ID: 1793019081218-->


Definiere die **PCL = Protocol Control Information** #flashcard
Information für die Partnerinstanz auf der gleichen Schicht.
**"Horizontale"** Kommunikation.
<!--ID: 1793019081225-->


Definiere die **PDU = Protocol Data Unit** #flashcard
Zusammenfassung von eigener SDU und PCI.
Wird die SDU der darunterliegenden Schicht.
(N+1)-PDU == (N)-SDU
<!--ID: 1793019081233-->


Definiere **Transparenz** bei einem in Schichten aufgebauten Kommunikationssystem. #flashcard
Die PDU der oberen Schichten wird von den unteren Schichten einfach als beliebige Nutzdaten angesehen. **Der Inhalt wird nicht betrachtet.**
<!--ID: 1793019081274-->



---


Nenen die **7 Schichten des ISO-OSI** Modells #flashcard
	7: Anwendung
	6: Darstellung
	5: Sitzung
	4: Transport
	3: Vermittlung
	2: Sicherung
	1: Bitübertragung
<!--ID: 1793019081278-->


Welche ISO-OSI Schichten sind **anwendungs- bzw. transportorientiert** #flashcard
5-7: Anwendungsorientiert
4-1: Transportorientiert
<!--ID: 1793019081282-->


Was zeichnet die **anwendungsorientierten** Schichten des ISO-OSI-Modells aus? #flashcard
- Semantik der Daten beachtet
- Kontext von früherer Kommunikation
- Steuerung des Kommunikationsablaufs
- Kompensation von Fehlverhalten
<!--ID: 1793019081287-->


Was zeichnet die **transportorientierten** Schichten des ISO-OSI-Modells aus? #flashcard
- Semantik der Daten irrelevant; transparent bzgl. Inhalt
- kein Bezug zur Kooperationsbeziehung der Dienstnutzer
- elementare Datenübertragung
<!--ID: 1793019081292-->
