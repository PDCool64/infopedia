---
tags:
  - PROGRA
status: rot
---
---

Exceptions treten auf wenn *zur Laufzeit* semantische Restriktionen nicht erfüllt werden.

Viele Exceptions werden automatisch geworfen, man kann aber auch selbst eigene Exception-Klassen definieren und selbst werfen.
# Klassifizierung
![[Pasted image 20260106161036.png]]

``Error``: Sehr schwerwiegende Fehler, von dem sich das Programm nicht sinnvoll erholen kann. Wird nicht gefangen und sollte nicht behandelt werden. (z.B. ``OutOfMemoryError``)

``Exception``: Behandelbarer Programmfehler. 
Wenn diese nicht gefangen werden, dann Programmabbruch
- ``RuntimeException``: sehr oft auftretende Exceptions - müssen *nicht* gefangen werden. Führen trotzdem zum Programmabsturz falls man sie nicht fängt.
- Alle anderen Exceptions (die keine U-Klassen von Exception, aber nicht von RuntimeException sind), müssen gefangen oder weitergereicht werden.
   Sie heißen "*checked exceptions*". 
   Bei einer checked exception muss eines von beiden gegeben sein:
   - ``catch (X x){...}`` Block: checked exception wird selbst gefangen
   - ``throws X`` in der Methodendeklaration: checked exception wird weitegereicht
   sonst beschwert sich der Compiler.

Die Klasse ``Throwable`` stellt einige Wichtige Methoden bereit, die oft sinnvoll zu überschreiben sind:
- ``getMessage()`` gibt die Fehlermeldung als ``String`` aus
- ``printStackTrace()`` macht smart shit
- ``toString()``
### Beispiele
- ``ArithmeticException``
- ``ArrayIndexOutOfBoundsException``
- ``NullPointerException``
- ``IOException`` - keine RuntimeException $\to$ checked
- ``ClassCastException``
- ``NumberFormatException`` (z.B. bei ``Interger.parseInt("hallo")``)
(alle anderen sind RuntimeExceptions)

# Syntax: ``try - catch - finally - throw``

Im ``try`` steht normaler Code, bei dem eine Exception auftreten kann.

Im ``catch`` stehen verschiedene *Patterns* die versuchen auftretende Fehler zu fangen.
	Die einzelnen Patterns werden von oben nach unten abgearbeitet und die erste passende verwendet. Sie *müssen* (wie bei ``switch`` ) von speziell->allgemein sortiert sein basierende auf den Unter->Oberklassen der Exception-Klassen.
	
Der `finally` Block wird anschließend *immer* ausgeführt.
	Egal ob Fehler aufgetreten oder nicht; Egal ob Fehler gefangen oder nicht.

```java

// === Deklaration eigner Exeptions ===
class NegativeNumberException extends Exception{
    int value;
    NegativeNumberException(int value){
        this.value = value;
    }
    @Override
    public String getMessage() {
        return "NegativeNumberException: "+value+"<0";
    }
}                          // Verschiedene Unterklassen möglich
class ToBigNumberException extends RuntimeException{
    int value;
    ToBigNumberException(int value){
        this.value = value;
    }
    @Override
    public String getMessage(){
        return "ToBigNumberException: "+value+" is too big";
    }
}
class RandomException extends Exception{ }




public class ExceptionDemo {
  
    // === Methode, die Fehler wirft === 
    public static String f(int i) throws RandomException, NegativeNumberException, ToBigNumberException {
        if (i<0)   throw new NegativeNumberException(i);
        if (i==13) throw new RandomException();
        if (i>100) throw new ToBigNumberException(i);
        
        return "Success!";
    }
    
    
    
    // === try-catch-finally um Fehler zu fangen ===
    
                                         //nicht alle Fehler gefangen
    public static void doSomething(int x) throws RandomException{
        
        try {
            String res = f(x);
        }
        catch ( NegativeNumberException nne){
            IO.println("Leider ist ein Fehler aufgetreten:"+nne.getMessage());
            IO.println("Bitte wähle also eine größere Zahl.");
        }
        catch ( ToBigNumberException tbne){
            IO.println("Leider ist ein Fehler aufgetreten:"+tbne.getMessage());
            IO.println("Bitte wähle also eine kleinere Zahl");
        }
        finally{
            IO.println("Bitte bewerten sie diese Methode mit 5/5 Sternen");
        }
    }
}
```

Es ist wie bei Patterns üblich auch möglich, eine leere Patternvariable zu verwenden, falls man das ``Exception`` Objekt selbst nicht braucht: ``catch (RandomException _ ) {...}`` 
# Exception handling in verschachtelten Methodenaufrufen
Wird ein Fehler in einer Methode nicht gefangen, dann springt die Programmausführung an den Aufrufenden Ort zurück. Dieser kann nun versuchen, den Fehler zu fangen. Schaft diese Methode es ebenfalls nicht, wird wieder an ihre aufrufende stelle zurückgesprungen.

Erreicht man bei diesen Sprüngen am Ende die ``main()`` und der Fehler wird auch dort nicht gefangen, so stürzt das Programm ab.

### Beispiel:
![[Pasted image 20260106164113.png]]