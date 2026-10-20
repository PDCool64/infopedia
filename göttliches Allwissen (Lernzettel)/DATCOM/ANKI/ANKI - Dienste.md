TARGET DECK: DATCOM::Dienste

4 typische **Dienstfunktionen** #flashcard
1. Connect
2. Disconnect
3. Data
4. Abort (Provider/Nutzer)
<!--ID: 1792416023439-->


4 typische Dienstprimitive #flashcard
1. Request: Anfordern eines Dienstes
2. Indication: Anzeige am Partner-SAP
3. Response: Antwort ausgehend vom Partner-SAP
4. Confirmation: Confirmation: Anzeige/Bestätigung der Diensterbringung am anfordernden SAP.
<!--ID: 1792416023444-->


Pfeiltypen in Ablaufdiagrammen #flashcard
- durchgezogen: ein konkretes Dienstprimitiv
- gestrichelt: kann sich um Zusammenfassung mehrerer Dienstprimitive für einfachere Darstellung handeln.
<!--ID: 1792416023448-->


Modell eines Kommunikationssystems: Schichten, Dienste, Protokolle #flashcard
![[Modell eines Kommunikationssystems.png]]
<!--ID: 1792416023452-->


Welche Primitive nutzt ein **unbestätigter** Dienst? #flashcard
1. Request
2. Indication
<!--ID: 1792416023455-->


Welche Primitive nutzt ein **bestätigter** Dienst? #flashcard
1. Request
2. Indication
3. Response
4. Confirmation
<!--ID: 1792416023459-->


Was ist bei der Nutzung von "Reponse" und "Indication" zu beachten? #flashcard
Werden _nur_ für Response$\to$Confirmation bei **bestätigten** Diensten genutzt.
False Friend: "Der Server schickt mir Daten also ist das Response". NEIN.
<!--ID: 1792416023463-->



Definition: verbindungsloser Dienst #flashcard 
- Dienstleistung ohne Kontext
- Jeder Datenaustausch wird isoliert betrachtet
- Kontrollparameter als Teil der übergebenen Daten
<!--ID: 1792416023467-->


Definition: verbindungsorientierter Dienst #flashcard
- Dienstleistung im Kontext, also abhängig von früher erbrachten Dienstleistungen
- Verbindungsaufbau = Aufbau von Kontext
- Aushandlung von Parametern
- Berücksichtigung des aktuellen Verbindungszustands bzw. Phase
- Weniger Kontrolldaten notwendig, aber Kontextmanagement
<!--ID: 1792416023470-->

