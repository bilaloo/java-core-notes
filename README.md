# Java-Core-Notes - Einführung in die Java-Welt

## Java Feature
**1. Einfach (Simple):** Java ist einfach zu erlernen und zu verstehen. Es wurde entwickelt, um eine klare und intuitive Syntax zu bieten.

**2. Portabel (Portable):** Java ist plattformunabhängig. Nach der Kompilierung wird der Java-Code in plattformunabhängigen Bytecode umgewandelt, der von der Java Virtual Machine (JVM) interpretiert wird.

**3. Objektorientiert (Object Oriented):** In Java ist alles ein Objekt. Die Sprache fördert die Verwendung von Objekten und Klassen, was zu modularerem und wartungsfreundlicherem Code führt.

**4. Sicher (Secured):** Java bietet eine hohe Sicherheit. Der Java-Code wird nach der Kompilierung in Bytecode umgewandelt, der für Menschen nicht lesbar ist. Außerdem verfügt Java über Sicherheitsmechanismen wie das Sandbox-Modell, um unerlaubten Zugriff auf Ressourcen zu verhindern.

**5. Robust:** Java bietet eine robuste Fehlerbehandlung und starke Speicherverwaltung. Es verhindert beispielsweise den Zugriff auf ungültige Speicherbereiche (Pointer Arithmetic), was dazu beiträgt, Speicherlecks und Programmabstürze zu vermeiden.

**6. Mehrfädig (Multi Threaded):** Java unterstützt Multithreading, wodurch mehrere Threads parallel ausgeführt werden können. Dies ermöglicht die effiziente Nutzung von Mehrkernprozessoren und die Erstellung reaktiver Anwendungen.

**7. Verteilt (Distributed):** Java bietet eingebaute Unterstützung für die Entwicklung von verteilten Anwendungen. RMI (Remote Method Invocation) und JNDI (Java Naming and Directory Interface) sind Beispiele für Java-Technologien, die bei der Entwicklung verteilter Anwendungen helfen.

**8. Architektonisch neutral (Architecture Neutral):** Der Java-Bytecode ist architektonisch neutral, was bedeutet, dass er auf verschiedenen Hardware-Plattformen ausgeführt werden kann, ohne dass Änderungen am Code erforderlich sind.

**9. Dynamisch (Dynamic):** Java ist eine dynamische Sprache. Es unterstützt Dinge wie Reflexion und die dynamische Erzeugung von Klassen zur Laufzeit.

Mögliche Interviewfragen:
- What are Java features?

### Java Programm Execution
- **Sample.java** (Source code) -> Compile to  -> **Simple.class** (Bytecode)
- The compiled file can run in any plattform by JVM (Java Virtual Machine)
- The JVM translate bytecode into native machine/platform code to make it understandable for that platform.
- JVM runs Java bytecode

Die Ausführung eines Java-Programms erfolgt in mehreren Schritten:
**1. Schreiben des Quellcodes:** Zuerst wird der Java-Quellcode in einer Datei mit der Erweiterung `.java` geschrieben. Zum Beispiel: `Sample.java`.
**2. Kompilieren des Quellcodes:** Der Quellcode wird mit einem Java-Compiler in sogenannten Bytecode übersetzt. Bytecode ist eine Zwischencodeform, die plattformunabhängig ist. Der kompilierte Bytecode wird in einer Datei mit der Erweiterung `.class` gespeichert. Zum Beispiel: `Sample.class`.
**3. Plattformunabhängigkeit:** Das kompilierte `.class`-Dateiformat ist plattformunabhängig, was bedeutet, dass es auf jeder Plattform ausgeführt werden kann, auf der eine Java Virtual Machine (JVM) verfügbar ist.
**4. Ausführung durch die JVM:** Um das Java-Programm auszuführen, wird die `.class`-Datei an die JVM übergeben. Die JVM ist eine Laufzeitumgebung, die auf der Zielplattform vorhanden sein muss. Sie liest den Bytecode und übersetzt ihn in nativen Maschinen- oder Plattformcode, der für die jeweilige Plattform verständlich ist.
**5. Ausführung des Bytecodes:** Die JVM führt den Java-Bytecode aus, indem sie ihn in nativen Code übersetzt und auf der Zielplattform ausführt. Dies ermöglicht die Ausführung des Java-Programms unabhängig von der zugrunde liegenden Hardware oder dem Betriebssystem.
###  JVM Architecture
-> Bild: JVM Architecture
Die JVM-Architektur besteht aus mehreren Komponenten, die zusammenarbeiten, um Java-Programme auszuführen:

1. **Class Loader:** Die Class Loader-Komponente lädt Java-Klassen von verschiedenen Quellen, wie z.B. dem lokalen Dateisystem oder dem Netzwerk, in den Speicher der JVM. Klassen werden dynamisch geladen, wenn sie zur Laufzeit benötigt werden.
   
2. **Runtime Data Areas:** Dies umfasst verschiedene Speicherbereiche, in denen Daten während der Programmausführung verwaltet werden:
    - **Method Area:** Hier werden Klassendefinitionen, statische Variablen und Methodeninformationen gespeichert.
    - **Heap:** Hier werden Objekte und deren Instanzvariablen gespeichert. Der Heap wird zur Laufzeit vom Garbage Collector verwaltet, um nicht mehr referenzierte Objekte zu entfernen.
    - **Stack:** Jeder Thread hat seinen eigenen Stack, auf dem Methodenaufrufe und lokale Variablen gespeichert werden. Diese Bereiche werden zur Laufzeit erstellt und verwaltet. (Zur Speicherung der tempäre Variablen)
    - **PC Registers:** Hier werden die Adressen der aktuellen auszuführenden Instruktionen für jeden Thread gespeichert.
    - **Native Method Stacks:** Hier werden Informationen für die Ausführung von nativen (nicht in Java geschriebenen) Methoden gespeichert.
      
3. **Execution Engine:** Die Execution Engine ist dafür verantwortlich, den maschinenspezifischen Bytecode in ausführbaren Maschinencode zu übersetzen. Es gibt verschiedene Ansätze zur Umsetzung, darunter die Interpretation und die Just-In-Time (JIT)-Kompilierung.
    
4. **Native Interface:** Die JVM bietet eine Schnittstelle, um mit nativem (plattformspezifischem) Code zu interagieren. Dies ermöglicht Java-Programmen, Funktionen von Betriebssystemen oder anderen Programmen zu nutzen, die nicht in Java geschrieben sind.
    
5. **Garbage Collector:** Die JVM enthält Mechanismen, um nicht mehr benötigte Objekte und Speicherbereiche zu erkennen und freizugeben. Dies ermöglicht eine effiziente Speicherverwaltung, ohne dass der Entwickler explizit Speicher freigeben muss.
    
6. **Java Native Interface (JNI):** Dies ist eine Schnittstelle, die es Java-Programmen ermöglicht, mit nativem Code (z.B. C oder C++) zu interagieren. Dies ist besonders nützlich für Aufgaben, die eine hohe Leistung erfordern oder auf plattformspezifische Funktionen zugreifen müssen.

- **Interpretation:** Bei der Interpretation liest die JVM den Java-Bytecode Zeile für Zeile und führt die entsprechenden Anweisungen aus, während sie den Code liest. Das bedeutet, dass der Bytecode nicht im Voraus in Maschinencode kompiliert wird, sondern zur Laufzeit in Echtzeit interpretiert wird
- 
Interview Question: 
- Erkläre JVM / JVM Architecture?
- Unterschied zwischen Compiler und Interpreter?
  Ein Compiler übersetzt den gesamten Quellcode auf einmal, bevor die Ausführung beginnt, während ein Interpreter den Quellcode zeilenweise interpretiert und ausführt.

## Java Runtime Enviroment (JRE)
Das Java Runtime Environment (JRE) ist eine Softwareumgebung, die zur Ausführung von Java-Anwendungen erforderlich ist. Es enthält die notwendigen Komponenten, um Java-Programme auszuführen, ohne dass Entwickler den Quellcode sehen oder bearbeiten müssen. Das JRE stellt die Laufzeitumgebung für Java-Anwendungen bereit und enthält die Java Virtual Machine (JVM) sowie wichtige Bibliotheken und Dateien, die für die Ausführung von Java-Code benötigt werden.

Das JDK enthält die folgenden Hauptkomponenten:
1. **JVM**
2. **Java Bibliotheken und Klassen**: z. B. Dateioperationen, Netzwerkkommunikation, GUI-Erstellung usw.
3. **Laufzeitdateien und -verzeichnisse**: z.B Konfigurationsdateien, Jar-Dateien, Ressourcen usw.
## Java Development Kit (JDK)
Das Java Development Kit (JDK) ist eine Softwareumgebung, die von Entwicklern verwendet wird, um Java-Anwendungen zu erstellen, zu kompilieren, zu debuggen und zu testen. Im Gegensatz zum Java Runtime Environment (JRE), das nur die notwendigen Komponenten für die Ausführung von Java-Anwendungen enthält, bietet das JDK eine vollständige Entwicklungsplattform mit Werkzeugen und Ressourcen, die für die Entwicklung von Java-Software erforderlich sind.

Das JDK enthält die folgenden Hauptkomponenten:
1. **Java Compiler**
2. **JVM**
3. **Java Libraries und APIs**
4. **Entwicklungswerkzeuge**: z.B Java compile (javac), Der Debugger (jdb) usw.
5. **Dokumentation und Beispiel-Code**

Zusammengefasst:  **JDK** enthält **JRE** und **JRE** enthält **JVM** 
- Unterschied zwischen JRE und JDK?
JRE -> für die Ausführung der Java-Code in einer Maschine.
JDK -> für die Entwicklung und Ausführung der Java-Code.

## JDK vs. JRE vs. JVM
**JDK (Java Development Kit):**
- Das JDK ist eine umfassende Entwicklungsplattform für die Erstellung von Java-Anwendungen.
- Es enthält den Java Compiler (`javac`), mit dem Java-Quellcode in Bytecode kompiliert wird.
- Es beinhaltet die Java Virtual Machine (JVM), die benötigt wird, um den generierten Bytecode auszuführen.
- Das JDK bietet eine Vielzahl von Entwicklungswerkzeugen wie Debugger (`jdb`), Profiler (`jvisualvm`), API-Dokumentation, Beispiele und Bibliotheken.
- Das JDK ist für Entwickler gedacht, die Java-Anwendungen erstellen, entwickeln, testen und debuggen möchten.

**JRE (Java Runtime Environment):**
- Das JRE ist eine Laufzeitumgebung, die erforderlich ist, um Java-Anwendungen auszuführen.
- Es enthält die Java Virtual Machine (JVM), die den Java-Bytecode interpretiert oder in nativen Maschinencode übersetzt.
- Das JRE stellt die notwendigen Laufzeitbibliotheken und -ressourcen bereit, um Java-Anwendungen in einer ausführbaren Umgebung zu betreiben.
- Das JRE ist für Endbenutzer gedacht, die Java-Anwendungen ausführen möchten, ohne den Quellcode zu bearbeiten oder zu entwickeln.

**JVM (Java Virtual Machine):**
- Die JVM ist eine abstrakte virtuelle Maschine, die Java-Bytecode ausführt.
- Sie ist Teil des JREs und des JDKs und ermöglicht die plattformübergreifende Ausführung von Java-Anwendungen.
- Die JVM interpretiert den Java-Bytecode oder übersetzt ihn in nativen Maschinencode, um die Ausführung zu beschleunigen.
- Die JVM verwaltet Speicher und Ressourcen für laufende Java-Anwendungen.

Zusammenfassend: Das **JDK** ist die Entwicklungsplattform, die Entwicklern alle Werkzeuge zum Erstellen von Java-Anwendungen zur Verfügung stellt. Das **JRE** ist die Laufzeitumgebung, die erforderlich ist, um Java-Anwendungen auszuführen. Die **JVM** ist die virtuelle Maschine, die den Java-Bytecode interpretiert oder übersetzt, um die Ausführung von Java-Anwendungen zu ermöglichen.
### Umgebung:
- Install java
- install JDK
- install Eclipse

- **Was ist der Zweck von Eclipse?** 
  Eclipse ist eine integrierte Entwicklungsumgebung (IDE), die für die Entwicklung von Software in verschiedenen Programmiersprachen verwendet wird. Sie bietet eine Plattform, auf der Entwickler Code schreiben, kompilieren, debuggen, testen und verwalten können.

## compile and run java program
- Compile the Program -> `javac filename.java`
- Execute the Program -> `java filename.class`


### Namenskonventionen in Java:

##### **Frage 1: Was sind Namenskonventionen in Java und warum sind sie wichtig?** 
Namenskonventionen in Java sind bestimmte Regeln und Konventionen, die festlegen, wie Bezeichner wie Klassen, Methoden, Variablen und Pakete benannt werden sollen. Sie helfen dabei, den Code lesbarer, konsistenter und verständlicher zu gestalten. Durch das Befolgen von Namenskonventionen wird der Code für Entwickler einfacher zu verstehen und zu warten, insbesondere wenn mehrere Entwickler an einem Projekt arbeiten.
#### **Klassen/Interfaces/Enums:**
- Für **Klassen**, **Interfaces**, **Enums** und **Ausnahmen** sollten mit einem Großbuchstaben beginnen und dann in CamelCase geschrieben werden.
- Sie dürfen nicht mit einer Ziffer, Sonderzeichen oder Leerzeichen beginnen.
#### **Methoden/Variablen/Objekte:**
- Für **Methoden**, **Variablen** und **Objekte** sollten mit einem Kleinbuchstaben beginnen und dann in CamelCase geschrieben werden.
- Sie dürfen nicht mit einer Ziffer, Sonderzeichen oder Leerzeichen beginnen.
#### **Pakete:**
- Paketnamen werden komplett in Kleinbuchstaben geschrieben, um Konflikte mit Klassen- oder Schnittstellennamen zu vermeiden.
#### **Konstanten:**
- Konstanten werden komplett in GROSSBUCHSTABEN geschrieben.


### Workspace (Arbeitsbereich), Package (Paket),  Namenskonventionen für Pakete

**Workspace (Arbeitsbereich):** Ein Workspace ist ein zentraler Ort, an dem du deine Projekte organisierst und entwickelst.

**Package (Paket):** Ein Paket ist eine organisatorische Einheit in Java, die Klassen, Schnittstellen und Ressourcen gruppieren hilft. 

**Namenskonventionen für Pakete:** Paketnamen sollten in Kleinbuchstaben geschrieben werden, um Konflikte zu vermeiden. Die Namen sollten umgekehrt zur Domain des Entwicklers sein, beginnend mit dem umgekehrten Domainnamen, um Eindeutigkeit zu gewährleisten. Zum Beispiel: `com.meinefirma.anwendung`. 


### Klassen und Objekte 
#### Klassen
Eine Klasse ist eine Vorlage oder ein Bauplan, der beschreibt, welche Eigenschaften (Attribute) und welche Aktionen (Methoden) ein bestimmtes Objekt haben kann. Klassen dienen dazu, Objekte zu erstellen, die auf ihren Eigenschaften und Verhaltensweisen basieren.

Modifier class ClassName {

}

Hier sind die Hauptbestandteile der Klassendefinition:
1. **Klassenname:** Der Name der Klasse, der den Bauplan repräsentiert. In Java und C++ beginnt der Klassenname normalerweise mit einem Großbuchstaben.
2. **Attribute:** Die Eigenschaften oder Variablen, die die Klasse beschreiben. Hier werden die Daten gespeichert, die ein Objekt der Klasse haben wird.
3. **Konstruktor:** Ein spezieller Methodentyp, der verwendet wird, um ein neues Objekt der Klasse zu erstellen und die Attribute zu initialisieren.
4. **Methoden:** Funktionen oder Aktionen, die von den Objekten dieser Klasse ausgeführt werden können.
#### Objekte
Ein Objekt ist eine Instanz einer Klasse. Es ist eine tatsächliche Einheit, die nach dem Muster der Klasse erstellt wird. Ein Objekt enthält Daten (Attribute) und Methoden, die in der Klasse definiert sind.
#### Arten von Klassen

**Abstrakte Klasse (Abstract Class):**
- Eine abstrakte Klasse ist eine Klasse, die nicht direkt instanziiert werden kann. Das bedeutet, du kannst keine Objekte direkt von einer abstrakten Klasse erstellen.
- Sie kann abstrakte Methoden enthalten, die in abgeleiteten Klassen implementiert werden müssen. Eine abstrakte Methode hat keine Implementierung in der abstrakten Klasse selbst.
- Abstrakte Klassen können sowohl abstrakte Methoden als auch konkrete Methoden enthalten.
- Abstrakte Klassen dienen oft als Basis für andere Klassen und legen eine gemeinsame Struktur oder Funktionalität fest, die von abgeleiteten Klassen verwendet wird.

**Nicht-abstrakte Klasse (Non-Abstract Class):**

- Eine nicht-abstrakte Klasse kann direkt instanziiert werden, um Objekte zu erstellen.
- Alle Methoden in einer nicht-abstrakten Klasse haben eine konkrete Implementierung, das heißt, sie haben einen Codeblock, der ausgeführt wird.
- Eine nicht-abstrakte Klasse kann von einer abstrakten Klasse erben und Methoden der abstrakten Klasse implementieren.
- Sie kann auch eigene Methoden und Attribute enthalten, die spezifisch für diese Klasse sind.

```java
// Abstrakte Klasse
abstract class Shape {
    abstract void draw(); // Abstrakte Methode
}

// Nicht-abstrakte Klasse, die von Shape erbt
class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle");
    }
}

public class Main {
    public static void main(String[] args) {
        Circle circle = new Circle();
        circle.draw();
    }
}
```

### Java Variables
**Variablen:** Variablen sind Speicherorte in einem Programm, in denen Werte gespeichert werden können. Sie werden verwendet, um Daten temporär zu speichern und auf sie zuzugreifen.

**Datentypen:** Datentypen definieren, welche Art von Daten in einer Variablen gespeichert werden kann. 

**Variablensyntax:**
`Datentyp variablenName = variablenWert;`

**Arten von Variablen:**

1. **Instanzvariablen:** An ein Objekt gebundene Variablen. Sie werden innerhalb einer Klasse, aber außerhalb von Methoden deklariert.
2. **Statische Variablen:** Auf die Klasse selbst bezogene Variablen. Alle Instanzen einer Klasse teilen sich denselben Wert für eine statische Variable.
3. **Lokale Variablen:** In einer Methode oder einem Codeblock deklarierte Variablen.
4. **Parameter (Methodenargumente):** Übergebene Werte an Methoden. Diese Parameter sind lokale Variablen, die beim Aufruf der Methode mit Werten belegt werden.
Hier ist ein einfaches Beispiel in Java, um die verschiedenen Arten von Variablen zu zeigen:
```java
public class VariablenBeispiel {
    // Instanzvariable
    int instanzVariable;

    // Statische Variable
    static int statischeVariable;

    public void methodeMitVariablen(int lokaleVariable) {
        // Lokale Variable
        int lokal = lokaleVariable;
    }

    public static void main(String[] args) {
        // Aufruf einer statischen Variable
        statischeVariable = 10;

        VariablenBeispiel objekt = new VariablenBeispiel();
        // Aufruf einer Instanzvariable
        objekt.instanzVariable = 20;

        // Aufruf einer Methode mit lokaler Variable
        objekt.methodeMitVariablen(30);
    }
}
```

## Datentypen
Datentypen in Java definieren, welche Art von Daten in einer Variablen gespeichert werden kann. Sie bestimmen auch die Größe des Speicherplatzes, den eine Variable benötigt.
Java Datentypen sind in zwei Hauptkategorien unterteilt.

**Primitive Datentypen:** Diese Datentypen repräsentieren grundlegende Werte und sind nicht auf Objekte angewiesen. Es gibt **acht** primitive Datentypen in Java:
1. **byte:** 8-Bit-Ganzzahl, Bereich von -128 bis 127.
2. **short:** 16-Bit-Ganzzahl, Bereich von -32,768 bis 32,767.
3. **int:** 32-Bit-Ganzzahl, Bereich von -2^31 bis 2^31 - 1.
4. **long:** 64-Bit-Ganzzahl, Bereich von -2^63 bis 2^63 - 1. (123124123L)
5. **float:** 32-Bit-Kommazahl mit begrenzter Genauigkeit. (0.3f)
6. **double:** 64-Bit-Kommazahl mit höherer Genauigkeit als float. (0.3d)
7. **char:** 16-Bit-Unicode-Zeichen.
8. **boolean:** Entweder `true` oder `false`.

**Referenzdatentypen:** Referenzdatentypen werden verwendet, um Objekte oder Instanzen von Klassen zu repräsentieren. Sie speichern Verweise auf die Speicheradressen der Objekte. 
In Java können Entwickler auch benutzerdefinierte Klassen erstellen, um eigene Datentypen zu definieren. Sie speichern nicht den Wert direkt, sondern eine Referenz auf den Speicherort des Werts. Beispiele: Klassen, Schnittstellen, Arrays.

```java
public class DatentypenBeispiel {
    public static void main(String[] args) {
        // Primitive Datentypen
        byte myByte = 10;
        short myShort = 1000;
        int myInt = 50000;
        long myLong = 1234567890L; // 'L' am Ende zeigt, dass es sich um einen long-Wert handelt
        float myFloat = 3.14f; // 'f' am Ende zeigt, dass es sich um einen float-Wert handelt
        double myDouble = 2.71828;
        char myChar = 'A';
        boolean myBoolean = true;

        // Referenzdatentyp (String)
        String myString = "Hallo, Welt!";
    }
}
```
Mögliche Interview Fragen:
1. **Was ist ein Datentyp?**
2. **Wie viele Datentypen gibt es in Java?** In Java gibt es zwei Hauptkategorien von Datentypen: primitive Datentypen und Referenzdatentypen.
3. **Erkläre die primitiven Datentypen in Java.** 
4. **Erkläre die Referenzdatentypen in Java?**

### Primitiven vs. Referenzdatentypen
Der Unterschied zwischen primitiven Datentypen und Referenzdatentypen liegt in der Art und Weise, wie sie Werte speichern, auf sie zugegriffen wird und wie sie im Speicher verwaltet werden:

**Primitive Datentypen:**
1. **Speicherplatz:** Primitive Datentypen speichern den Wert direkt im Speicher. Ihre Größe ist fixiert und hängt von jedem Datentyp ab.
2. **Wertzuweisung:** Beim Zuweisen eines Wertes zu einer primitiven Variable wird der Wert selbst in der Variable gespeichert.
3. **Operationen:** Primitive Datentypen unterstützen grundlegende mathematische Operationen und Vergleichsoperationen.
4. **Performance:** Da die Werte direkt gespeichert werden, sind primitive Datentypen in der Regel schneller in der Verarbeitung.

Beispiele für primitive Datentypen in Java sind `int`, `double`, `char`, `boolean`, usw.

**Referenzdatentypen:**
1. **Speicherplatz:** Referenzdatentypen speichern keine Werte direkt, sondern speichern eine Referenz auf den Speicherort des Wertes im Speicher.
2. **Wertzuweisung:** Bei der Zuweisung eines Wertes zu einer Referenzvariable wird die Referenz auf den Speicherort des Wertes gespeichert, nicht der Wert selbst.
3. **Operationen:** Referenzdatentypen ermöglichen den Zugriff auf die Methoden und Attribute der zugrunde liegenden Klasse oder des Objekts.
4. **Performance:** Aufgrund der indirekten Referenzierung können Referenzdatentypen etwas langsamer in der Verarbeitung sein als primitive Datentypen.

Beispiele für Referenzdatentypen in Java sind Klassen, Schnittstellen, Arrays, usw.


## Operatoren
Operatoren werden verwendet, um Berechnungen, Vergleiche und logische Verknüpfungen in Programmen durchzuführen.
Operatoren können in verschiedene Kategorien unterteilt werden:

**1. Arithmetische Operatoren:** Diese Operatoren werden verwendet, um mathematische Berechnungen durchzuführen.
- `+`: Addition
- `-`: Subtraktion
- `*`: Multiplikation
- `/`: Division
- `%`: Modulo (Restwert)

**2. Vergleichsoperatoren:** Diese Operatoren werden verwendet, um Werte zu vergleichen und Wahrheitswerte zu erzeugen.
- `==`: Gleichheit
- `!=`: Ungleichheit
- `<`: Kleiner als
- `>`: Größer als
- `<=`: Kleiner oder gleich
- `>=`: Größer oder gleich

**3. Logische Operatoren:** Diese Operatoren werden verwendet, um logische Ausdrücke zu verknüpfen.
- `&&`: Logisches UND (AND)
- `||`: Logisches ODER (OR)
- `!`: Logisches NICHT (NOT)

**4. Zuweisungsoperatoren:** Diese Operatoren werden verwendet, um Werte Variablen zuzuweisen.
- `=`: Wertzuweisung
- `+=`: Addition und Zuweisung
- `-=`: Subtraktion und Zuweisung
- `*=`: Multiplikation und Zuweisung
- `/=`: Division und Zuweisung
- `%=`: Modulo und Zuweisung

**5. Inkrement-/Dekrementoperatoren:** Diese Operatoren werden verwendet, um den Wert einer Variable um 1 zu erhöhen oder zu verringern.
- `++`: Inkrement (Erhöhung um 1)
- `--`: Dekrement (Verringerung um 1)

**6. Bitweise Operatoren:** Diese Operatoren werden auf Bit-Ebene verwendet.
- `&`: Bitweises UND -> Wenn beide Bits an der gleichen Position Eins sind, wird das Ergebnisbit an dieser Position Eins, ansonsten Null.
- `|`: Bitweises ODER -> Wenn eines der Bits an der gleichen Position Eins ist, wird das Ergebnisbit an dieser Position Eins, andernfalls Null.
- `^`: Bitweises XOR (ausschließendes ODER) -> Wenn die Bits an der gleichen Position unterschiedlich sind, wird das Ergebnisbit an dieser Position Eins, andernfalls Null.
- `~`: Bitweises NICHT -> Kehrt die Bits um, d.h. Einsen werden zu Nullen und umgekehrt.
- `<<`: Bitweiter Linksverschiebung -> Neue Bits werden auf der rechten Seite mit Nullen aufgefüllt.
- `>>`: Bitweite Rechtsverschiebung (arithmetisch) -> Neue Bits werden auf der linken Seite mit den ursprünglichen Vorzeichenbits (arithmetische Rechtsverschiebung) oder Nullen (logische Rechtsverschiebung) aufgefüllt.
- `>>>`: Bitweite Rechtsverschiebung (logisch) -> Ähnlich wie `>>`, aber füllt immer mit Nullen auf, unabhängig vom Vorzeichen der Zahl.
```java
int a = 4;
int b = 5;
System.out.println(a & b); // 4
System.out.println(a | b); // 5
System.out.println(a ^ b); // 1
System.out.println(a << b); // 16
System.out.println(a >> b); // 1
System.out.println(~b); // -6
System.out.println(~-10); // 9
```

7. **Bedingter (Ternärer) Operator:** Ein bedingter Operator ermöglicht es, abhängig von einer Bedingung, einen von zwei Werten auszuwählen.
    - Bedingter Operator ( ? : ) -> `Bedingung ? Wert_für_wahr : Wert_für_falsch;`
    ```java
    int zahl = 10;
	String ergebnis = (zahl > 5) ? "Größer als 5" : "Kleiner oder gleich 5";
	```


## Type Casting
```java
float floatNumber = 100.0f;
int intNumber = (int)floatNumber;
```
**1. Was ist Typkonvertierung in Java?** ist die Umwandlung eines Datentyps in einen anderen.  Es gibt zwei Arten von Typkonvertierungen: implizite (automatische) Konvertierung und explizite (manuelle) Konvertierung.

**2. Was ist "Widening" in Java?** "Widening" bezieht sich auf die implizite Typkonvertierung von einem Datentyp mit kleinerer Größe in einen Datentyp mit größerer Größe. Dies geschieht automatisch, da keine Daten verloren gehen. Zum Beispiel wird eine Ganzzahl (`int`) in einen Fließkommawert (`double`) umgewandelt.

**3. Was ist "Narrowing" in Java?** "Narrowing" bezieht sich auf die explizite Typkonvertierung von einem Datentyp mit größerer Größe in einen Datentyp mit kleinerer Größe. Da Daten verloren gehen könnten, muss diese Konvertierung manuell durchgeführt werden. Zum Beispiel könnte ein `double` in ein `int` umgewandelt werden.

**4. Was ist implizite Konvertierung in Java?** Implizite Konvertierung, auch als automatische Konvertierung bekannt, tritt auf, wenn Java selbstständig Datentypen konvertiert, um sicherzustellen, dass Daten nicht verloren gehen. Beispielsweise wird eine Ganzzahl in eine Gleitkommazahl umgewandelt, wenn sie in einer Berechnung mit Gleitkommazahlen verwendet wird.
```java
int n1 = 100
float n2 = n1 // Die Umwandlung wird funktionieren.
```

**5. Was ist explizite Konvertierung in Java?** Explizite Konvertierung tritt auf, wenn du manuell eine Datentypkonvertierung durchführst, indem du den gewünschten Datentyp in Klammern vor den Wert schreibst. Dies ist notwendig, wenn Daten bei der Konvertierung verloren gehen könnten, z. B. wenn du eine Gleitkommazahl in eine Ganzzahl umwandelst.
```java
float n1 = 100
int n2 = n1 // Die Umwandlung wird NICHT funktionieren.

float n1 = 100 
int n2 = (int)n1 // Die Umwandlung wird funktionieren.
```

**1. Was ist eine Wrapper-Klasse in Java?** 
Eine Wrapper-Klasse in Java ist eine Klasse, die eine primitive Datenart (wie int, char, boolean usw.) in ein Objekt einhüllt. Jeder primitiven Datentyp in Java hat eine entsprechende Wrapper-Klasse. Zum Beispiel ist die Wrapper-Klasse für den Datentyp `int` die Klasse `Integer`. Diese Wrapper-Klassen bieten Methoden und Funktionen, die es ermöglichen, mit primitiven Datentypen als Objekten zu arbeiten.

**2. Wofür dienen Wrapper-Klassen in Java?** Wrapper-Klassen haben verschiedene Verwendungszwecke, darunter:
- Konvertierung von primitiven Datentypen in Objekte, um sie in Sammlungen wie Listen oder Sets zu speichern.
- Bereitstellung von Methoden zum Arbeiten mit primitiven Datentypen als Objekten.
- Erlauben von Null-Werten für primitive Datentypen durch Verwendung von `null`.
- Generics in Java funktionieren nur mit Objekten und unterstützen keine primitiven Datentypen.
- Sammlungen (Collections) in Java arbeiten nur mit Objekten. Um primitive Datentypen in einer dieser Klassen zu speichern, musst du den primitiven Datentyp in eine Klasse verpacken..

**3. Was ist Autoboxing in Java?** 
Autoboxing ist ein automatischer Prozess in Java, bei dem primitiven Datentypen automatisch in ihre entsprechenden Wrapper-Klassen umgewandelt werden. Dies ermöglicht es, primitiven Datentypen in Sammlungen wie ArrayLists zu speichern, die normalerweise Objekte erfordern.

**4. Was ist Auto-Unboxing in Java?** 
Auto-Unboxing ist der umgekehrte Prozess von Autoboxing. Hierbei wird ein Objekt einer Wrapper-Klasse automatisch in einen primitiven Datentyp umgewandelt. Dies geschieht, wenn ein Objekt in einem Kontext verwendet wird, in dem ein primitiver Datentyp erwartet wird.

```java
// Autoboxing: primitive int wird automatisch in Integer umgewandelt
Integer zahlObjekt = 42;

// Auto-Unboxing: Wert aus dem Integer-Objekt wird automatisch extrahiert
int zahl = zahlObjekt;

// Beispiel mit ArrayList (Sammlung von Integer-Objekten)
ArrayList<Integer> zahlenListe = new ArrayList<>();
zahlenListe.add(10); // Autoboxing: 10 wird in Integer umgewandelt

int ersterWert = zahlenListe.get(0); // Auto-Unboxing: Wert wird in int umgewandelt

// Auto-Unboxing
Integer i = 10;
if (i == 123) { // Integer == int 
	System.out.println("This is an Integer....");
}
```


##### Primitive Type zu Wrapper Class
Es gibt zwei gängige Möglichkeiten, einen primitiven Datentyp in eine Wrapper-Klasse umzuwandeln: 
- die Verwendung von Konstruktoren 
- die Verwendung von statischen Methoden wie `valueOf()`.

**1. Verwendung von Konstruktoren:** 
Jede Wrapper-Klasse hat einen oder mehrere Konstruktoren, die primitiven Datentypen als Argumente akzeptieren und ein entsprechendes Wrapper-Objekt erstellen.
```java
int primitiveInt = 42;
Integer wrapperInt = new Integer(primitiveInt); // Konstruktor für Integer
```
**2. Verwendung von statischen Methoden wie `valueOf()`:** 
Wrapper-Klassen bieten oft eine statische Methode namens `valueOf()`, die einen primitiven Wert als Argument akzeptiert und ein entsprechendes Wrapper-Objekt zurückgibt.
```java
double primitiveDouble = 3.14;
Double wrapperDouble = Double.valueOf(primitiveDouble); // Verwendung von valueOf für Double
```
Die Verwendung von `valueOf()` wird oft bevorzugt, da sie möglicherweise effizienter ist, da sie möglicherweise wiederverwendete Objekte zurückgibt.
Weitere Beispiele:
```java
int primitiveInt = 42;
Integer wrapperInt = Integer.valueOf(primitiveInt);

float primitiveFloat = 3.14f;
Float wrapperFloat = Float.valueOf(primitiveFloat);

char primitiveChar = 'A';
Character wrapperChar = Character.valueOf(primitiveChar);

boolean primitiveBoolean = true;
Boolean wrapperBoolean = Boolean.valueOf(primitiveBoolean);
```

##### Wrapper-Klasse in primitiven Datentyp umwandeln:
Du kannst eine Wrapper-Klasse in einen primitiven Datentyp umwandeln, indem du entsprechende Methoden aufrufst, die in den Wrapper-Klassen verfügbar sind. Jede Wrapper-Klasse bietet Methoden, um ihren Wert als primitiven Datentyp zurückzugeben.
```java
Integer wrapperInt = Integer.valueOf(42);
int primitiveInt = wrapperInt.intValue(); // Methode intValue() gibt den Wert als int zurück

Double wrapperDouble = Double.valueOf(3.14);
double primitiveDouble = wrapperDouble.doubleValue();

Character wrapperChar = Character.valueOf('A');
char primitiveChar = wrapperChar.charValue();

```


## Methoden
- In Java sind Methoden dafür, bestimmte Aktionen oder Operationen auszuführen.
- Sie sind in Klassen definiert und können aufgerufen werden.
- Methoden ermöglichen die Wiederverwendung von Code und verbessert Lesbarkeit.

Note: **Rückgabetyp in Methoden:** Der Datentyp des Werts, den die Methode zurückgibt. Verwendung von `void`, wenn die Methode keinen Wert zurückgibt.
#### Zugriffsmodifikatoren:** 
Diese Modifikatoren regeln den Zugriff auf Klassen, Methoden und Variablen.
- `public`: Das Element ist von überall aus sichtbar.
- `protected`: Das Element ist in der eigenen Klasse, abgeleiteten Klassen und im selben Paket sichtbar.
- `default` (kein Modifikator angegeben): Das Element ist nur im selben Paket sichtbar.
- `private`: Das Element ist nur in der eigenen Klasse sichtbar. Klassen und Interface können nicht als `private` deklariert werden. Wenn eine Klasse einen `private` Konstruktor hat, ist es nicht möglich außerhalb der Klasse Objekte zu erstellen.
```java
com (package)
└── library (project1)
    ├── books
    │   ├── Book.java
    │   ├── FictionBook.java
    │   └── NonFictionBook.java
    ├── members (project2)
    │   ├── LibraryMember.java
    │   ├── StudentMember.java
    │   └── FacultyMember.java
    └── LibraryApp.java
```

#### Nichtzugriffsmodifikatoren:** 
Diese Modifikatoren beeinflussen das Verhalten und die Funktionalität von Klassen und Methoden, haben jedoch keinen direkten Einfluss auf den Zugriffsbereich..
- `static`: Das Element gehört zur Klasse und nicht zu einer Instanz. Es kann aufgerufen werden, ohne ein Objekt zu erstellen.
- `final`: Das Element kann nicht erneut zugewiesen oder vererbt werden. Bei Methoden bedeutet `final`, dass die Methode nicht in abgeleiteten Klassen überschrieben werden kann.
- `abstract`: Das Element ist abstrakt und hat keine Implementierung. Es wird in abgeleiteten Klassen implementiert.
- `synchronized`: In Mehrfadenanwendungen stellt sicher, dass nur ein Thread gleichzeitig auf das Element zugreifen kann.
- `volatile`: In Mehrfadenanwendungen stellt sicher, dass Änderungen an dieser Variable sofort von allen Threads sichtbar sind.
- `transient`: Wird für Instanzvariablen verwendet, um anzuzeigen, dass sie nicht in den Zustand eines serialisierten Objekts einbezogen werden sollen.

new keyword -> um Objekte zu erstellen.

```java
public class MethodenBeispiel {

    // Methode zur Addition von zwei Zahlen
    public int addiere(int zahl1, int zahl2) {
        int ergebnis = zahl1 + zahl2;
        return ergebnis;
    }

    public static void main(String[] args) {
        MethodenBeispiel beispiel = new MethodenBeispiel();
        int summe = beispiel.addiere(5, 3);
        System.out.println("Die Summe ist: " + summe);
    }
}

```

Interviewfrage:
- How to achieve reusability in java?
Mithilfe von Methoden kann man die Wiederverwendbarkeit erreichen.


## Variables in Java

#### Local Variables 
- Lokale Variablen werden innerhalb einer Methode, eines Konstruktors oder von Blöcken definiert. 
- Der Gültigkeitsbereich dieser Variable ist auf die Methode, den Konstruktor oder den Block beschränkt. 
- Es können keine Zugriffsmodifikatoren für lokale Variablen verwendet werden.
- Dies sind temporäre Variablen, die während der Ausführung der Methode existieren. 
- Sie sind nicht aus dem Rest der Klasse heraus zugänglich.
#### Instance Variables
- Instanzvariablen werden innerhalb einer Klasse, aber außerhalb von Methoden, definiert. 
- Jede Instanz (Objekt) einer Klasse enthält ihre eigene Kopie dieser Variablen. 
- Wenn ein Objekt mit dem Schlüsselwort `new` erstellt wird, werden Instanzvariablen erstellt, und wenn das Objekt zerstört wird, wird auch die Instanzvariable zerstört.
- Instanzvariablen können Zugriffsmodifikatoren haben. 
- Instanzvariablen sind für alle Methoden, Konstruktoren und Blöcke in der Klasse sichtbar. 
- Instanzvariablen können innerhalb der Klasse direkt aufgerufen werden, indem der Variablennamen verwendet wird. 
- Instanzvariablen sind nicht-statische Variablen. 
- Sie werden auch als Zustandsvariablen (State Variables) bezeichnet.
#### Static Variables (Statische Variablen)
- Das statische Schlüsselwort wird hauptsächlich für die Speicherverwaltung verwendet. 
- Das statische Schlüsselwort ist mit der Klasse selbst und nicht mit einer Instanz der Klasse verbunden. 
- Durch die Verwendung von statischen Variablen machen wir unser Programm speichereffizient. 
- Um auf eine statische Variable oder Methode zuzugreifen, verwenden wir den Klassennamen und nicht eine Instanz der Klasse.
- Das statische Schlüsselwort kann mit
   - Variablen 
   - Methoden 
   - Imports 
   - Blöcken 
   - Klassen 
     verwendet werden.
- Statische Methoden können nicht direkt auf nicht-statische Variablen oder Methoden zugreifen. 
- Die Schlüsselwörter `this` und `super` können nicht im statischen Kontext verwendet werden
- Only one copy on the variables at runtime

##### Vorteile des statischen Schlüsselworts: 
- Globale Zugänglichkeit: Das bedeutet, dass es nicht von einer Instanz der Klasse abhängig ist.
- Daher kann es über den Klassennamen aufgerufen werden (kein Objekt ist erforderlich). 
- Nur eine Instanz pro JVM. 
- Statische Mitglieder beeinflussen nicht den Zustand des Objekts. 
- Sie werden beim Start der JVM geladen und beim Herunterfahren der JVM zerstört.

##### Nachteile des statischen Schlüsselworts: 
- Diese sind immer Teil des Klassenspeichers, unabhängig davon, ob sie verwendet werden oder nicht. 
- Erzeugen und Löschen von statischen Variablen können nicht kontrolliert werden. 
- Statische Methoden können nicht überschrieben werden. 
- Wenn ein Thread den statischen Wert ändert, kann dies die Funktionalität anderer Threads beeinträchtigen.
##### Das ist kein speichereffizient!!!
```java
public class Employee { // Das ist kein speichereffizient!!!
    int empId;
    String name;
    String company;

	public void printInformation(int empId, String name, String company){
		System.out.println("empId:" + empId + " - " + " name:" + name + " - " + "company: " + company);
	}

    public static void main(String[] args) {
        Employee employeeData = new Employee();
        employeeData.printInformation(101, "Karim", "Oracle");
        employeeData.printInformation(202, "Alex", "Oracle")
    }
}
```
##### Das ist  speichereffizient :)
```java
public class Employee { // Das ist kein speichereffizient!!!
    int empId;
    String name;
    static String company = "Oracle";

	public void printInformation(int empId, String name){
		System.out.println("empId:" + empId + " - " + " name:" + name + " - company: " + Employee.company);
	}

    public static void main(String[] args) {
        Employee employeeData = new Employee();
        employeeData.printInformation(101, "Karim");
		employeeData.printInformation(202, "Alex");
		System.out.print("Company: "+ Employee.company);
    }
}
```

## Static schlüsselwort

#### Static Methods / Statische Methoden
Statische Methoden sind Methoden, die auf Klassenebene existieren und nicht an eine Instanz der Klasse gebunden sind. Sie können direkt über den Klassennamen aufgerufen werden, ohne eine Instanz der Klasse erstellen zu müssen.
- Du kannst nur auf statische Variablen in statischen Methoden zugreifen. Wenn du versuchst, auf eine nicht-statische Variable zuzugreifen, wird der Compiler einen Fehler melden.
- Statische Methoden können über ihre Klassenreferenz aufgerufen werden, und es ist nicht erforderlich, eine Instanz der Klasse zu erstellen. 
- Statische Methoden gehören ebenfalls zum Klassenniveau des Gültigkeitsbereichs.
```java
public class StaticMethodExample {

	static int staticNum = 20; // In einer statischen Methode nicht aufrufbar!!!
    // Statische Methode, die zwei Zahlen addiert
    public static int addiere(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int summeClassMethod = StaticMethodExample.addiere(5, 3); // Aufruf der statischen Methode
        int summeMethod = addiere(5, 3); // Aufruf der statischen Methode
        System.out.println("Die Summe ist: " + summeClassMethod);
        System.out.println("Die Summe ist: " + summeMethod);
    }
}
```

#### Static import / Statische Importe
Statische Importe ermöglichen es, statische Mitglieder (Variablen und Methoden) einer Klasse direkt zu verwenden, ohne den Klassennamen zu qualifizieren.
- Mit static import:
```java
import static java.lang.Math.*;
import static java.lang.Sytem.*;

public class StaticImportExample {

    public static void main(String[] args) {
        double wurzel = sqrt(25); // Direkter Zugriff auf die statische Methode sqrt
        out.println("Wurzel von 25 ist: " + wurzel);
    }
}
```
- Ohne static import
```java
public class StaticImportExample {

    public static void main(String[] args) {
        double wurzel = Math.sqrt(25); // Indirekter Zugriff auf die statische Methode sqrt
        System.out.println("Wurzel von 25 ist: " + wurzel);
    }
}
```
#### Static block / Statische Blöcke:
Statische Blöcke sind Codeblöcke innerhalb einer Klasse, die mit dem Schlüsselwort `static` markiert sind. Sie werden beim Laden der Klasse ausgeführt, noch bevor eine Instanz erstellt wird oder statische Methoden aufgerufen werden. Statische Blöcke werden oft verwendet, um Initialisierungscode auszuführen. Blöcke werden ausgeführt, wenn die Klasse im Speicher geladen wird.
```java
public class StaticBlockExample {

    static {
        System.out.println("Dieser statische Block wird beim Laden der Klasse ausgeführt.");
    }

    public static void main(String[] args) {
        System.out.println("Hauptmethode aufgerufen.");
    }
}

```
**Verwendung von statischen Blöcken:** 
Statische Blöcke werden häufig verwendet, um Initialisierungscode auszuführen, der einmalig beim Laden der Klasse benötigt wird. Dies kann das Konfigurieren von statischen Variablen, das Öffnen von Ressourcen oder das Durchführen von anderen Aufgaben sein, die beim Start der Klasse durchgeführt werden müssen.

#### Static Class / Statische Klassen (innere statische Klassen)
Statische Klassen sind innere Klassen, die mit dem Schlüsselwort `static` deklariert werden. Sie sind unabhängig von Instanzen der äußeren Klasse und können instanziiert werden, ohne eine Instanz der äußeren Klasse zu erstellen. Sie werden oft verwendet, um Klassen zu gruppieren, die eng miteinander verbunden sind, aber keine spezifische Instanzbeziehung benötigen.
```java
public class OuterClass {

    // Innere statische Klasse
    static class InnerStaticClass {
	    static int num1 = 1; // statische Variable direkt zugänglich
	    int num2 = 2; // zugänglich durch die Erstellung einer Instanz
	    
        void anzeigen() {
            System.out.println("Dies ist die innere statische Klasse.");
        }
    }

    public static void main(String[] args) {
        InnerStaticClass inner = new InnerStaticClass();
        inner.anzeigen(); // Aufruf der Methode in der inneren statischen Klasse
    }
}
```


Was bedeute das Schlüsselwort "static"?
Das Schlüsselwort "static" in Java hat mehrere Bedeutungen und Anwendungen, die das Verhalten von Klassen, Variablen und Methoden beeinflussen können. Im Allgemeinen kennzeichnet das "static" Schlüsselwort Elemente, die auf Klassenebene existieren und nicht an eine bestimmte Instanz der Klasse gebunden sind

## Arrays
Arrays in Java sind Datenstrukturen, die verwendet werden, um eine Sammlung von Elementen eines bestimmten Datentyps zu speichern. Ein Array ermöglicht es, mehrere Werte desselben Datentyps in einer einzigen Variablen zu speichern und darauf zuzugreifen

**Eigenschaften von Arrays:**
- Arrays haben eine feste Größe, die bei der Erstellung festgelegt wird und später nicht geändert werden kann.
- Die Elemente in einem Array sind von gleicher Art und Größe. Zum Beispiel können Sie ein Array von Ganzzahlen, Gleitkommazahlen oder Zeichen erstellen.
- Die Indizes in einem Array beginnen normalerweise bei 0 und reichen bis zur Größe des Arrays minus 1.
#### Primitive Datentypen und Objekte einer Klasse
Ein Array kann sowohl primitive Datentypen als auch Objekte einer Klasse enthalten, abhängig von der Definition des Arrays. In beiden Fällen werden die Daten in speziellen Speicherbereichen gespeichert.
- Im Fall von primitiven Datentypen werden die tatsächlichen Werte in aufeinanderfolgenden Speicherorten gespeichert. Dies ermöglicht einen schnellen und direkten Zugriff auf die Daten.
  ```java
  int[] zahlen = {5, 10, 15, 20};
  char[] zeichen = {'a', 'b', 'c', 'd'};
  ```
- Im Fall von Objekten einer Klasse werden die eigentlichen Objekte im Heap-Segment gespeichert. Der Heap ist der Bereich des Speichers, in dem Objekte während der Laufzeit des Programms dynamisch zugewiesen und verwaltet werden. Das Array speichert Referenzen auf die Speicheradressen der einzelnen Objekte.
	```java
	  class Person {
	    String name;
	    int alter;
	
	    public Person(String name, int alter) {
	        this.name = name;
	        this.alter = alter;
	    }
	}
	
	public class ObjectArrayExample {
	    public static void main(String[] args) {
	        Person[] personen = new Person[3];
	        personen[0] = new Person("Alice", 25);
	        personen[1] = new Person("Bob", 30);
	        personen[2] = new Person("Carol", 28);
	        
	        System.out.println(personen[0].name); // Ausgabe: Alice
			System.out.println(personen[1].alter); // Ausgabe: 30
	    }
	}
	```

##### eindimensionale, zweidimensionale, dreidimensionale oder vierdimensionale Arrays klassifizieren
1. Eindimensionale Arrays
```java
int[] eindimensionalesArray = {10, 20, 30, 40, 50};
```
2. Zweidimensionale Arrays
```java
int[][] zweidimensionalesArray = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```
3. Dreidimensionale Arrays
```java
int[][][] dreidimensionalesArray = {
    {
        {1, 2},
        {3, 4}
    },
    {
        {5, 6},
        {7, 8}
    }
};
```

Beispiele:
```java
int[] numbers;
numbers = new int[5];

int[] numbers = new int[5];

int[] numbers = {1,2,3,4,5};
// oder 
int numbers[] = {1,2,3,4,5};

numbers[0] = 100;
numbers[1] = 101;
numbers[2] = 102;
numbers[3] = 103;
numbers[4] = 104;

System.out.println("Array Länge: "+ numbers.length);
```

## Constructor / Konstruktoren
Konstruktoren in Java sind spezielle Methoden in einer Klasse, die verwendet werden, um Objekte zu erstellen und zu initialisieren. 
- Der Name des Konstruktors muss exakt dem Namen der Klasse entsprechen
- Konstruktoren haben keinen Rückgabetyp, nicht einmal `void`. 
- Konstruktoren werden automatisch aufgerufen, wenn ein neues Objekt erstellt wird, und sie ermöglichen die Initialisierung von Instanzvariablen und die Ausführung von Initialisierungscode.
- Wenn Sie keinen Konstruktor in einer Klasse definieren, erstellt Java standardmäßig einen standardmäßigen Konstruktor ohne Parameter (Default-Konstruktor).

##### Arten von Konstruktoren
1. Default Construtore / Standard Konstruktor
   Java erstellt einen standardmäßigen Konstruktor ohne Parameter, wenn eine Klasse keine Konstruktor hat.
2. No-Arg Constructor /  No-Arg Konstruktor
   Genau wie Standard-Konstruktor aber die Konstruktor ist in der Klasse sichtbar:
```java
public class Person {
    String name;
    int alter;

    // Standardkonstruktor ohne Parameter
    public Person() {
        name = "Unbekannt";
        alter = 0;
    }
}
``` 
3. Paramterized Constructor / Parameterisierter Konstruktor
   Ein parameterisierter Konstruktor nimmt Parameter entgegen, um die Instanzvariablen während der Objekterstellung zu initialisieren.
```java
public class Person {
    String name;
    int alter;

    // Parameterisierter Konstruktor
    public Person(String n, int a) {
        name = n;
        alter = a;
    }
}
```
##### Aufruf von Konstruktoren 
Konstruktoren können durch das Schlüsselwort `new` aufgerufen werden, gefolgt von der Klassenbezeichnung und den erforderlichen Parametern.
```java
public class ConstructorExample {
    public static void main(String[] args) {
        Person person1 = new Person(); // Aufruf des Standardkonstruktors
        Person person2 = new Person("Alice", 25); // Aufruf des parameterisierten Konstruktors
    }
}
```

##### Konstruktor vs. Methode
1. **Zweck**:
   - **Konstruktor**: um ein neues Objekt zu erstellen und zu initialisieren. 
   - **Methode**: Eine Methode ist eine Gruppe von Anweisungen, die eine bestimmte Aufgabe ausführt.
2. **Rückgabe**:
   - **Konstruktor**: Ein Konstruktor hat keinen Rückgabetyp. Seine Hauptaufgabe besteht darin, ein neues Objekt zu initialisieren.
   - **Methode**: Eine Methode hat normalerweise einen Rückgabetyp, der angibt, welchen Datentyp sie zurückgibt. Wenn die Methode keinen Wert zurückgibt, wird der Rückgabetyp als `void` deklariert.
3. **Name**:
   - **Konstruktor**: Der Name eines Konstruktors muss exakt dem Namen der Klasse entsprechen.
   - **Methode**: Methodennamen sind frei wählbar, solange sie den Regeln für Bezeichner in Java folgen.
4. **Aufruf**:
   - **Konstruktor**: Konstruktoren werden automatisch aufgerufen, wenn ein neues Objekt erstellt wird.
   - **Methode**: Methoden werden explizit durch ihren Namen aufgerufen.
5. **Verwendung**:
   - **Konstruktor**: Konstruktoren werden verwendet, um Objekte zu erstellen und zu initialisieren. Sie legen den Anfangszustand eines Objekts fest
   - **Methode**: Methoden werden verwendet, um wiederholbare Operationen oder Aktionen auszuführen.

```java
public class Person {
    String name;
    int alter;
 
	// Standard Konstruktor
    public Person() {
        name = "Ibrahim";
        alter = 23;
    }
    
    // Konstruktor
    public Person(String n, int a) {
        name = n;
        alter = a;
    }

    // Methode
    public void printDetails() {
        System.out.println("Name: " + name);
        System.out.println("Alter: " + alter);
    }
}

public class ConstructorVsMethodExample {
    public static void main(String[] args) {
	    // Aufruf des Standard-Konstruktors
        Person standardPerson = new Person(); 
        // Aufruf des parameterisierten Konstruktors
        Person PermeterizedPerson = new Person("Alice", 25);
         
        PermeterizedPerson.printDetails(); // Aufruf der Methode       
        standardPerson.printDetails(); // Aufruf der Methode
    }
}

```

Mögliche Interviewfragen:
1. **Was ist ein Konstruktor?** Ein Konstruktor ist eine spezielle Methode in einer Klasse, die verwendet wird, um ein Objekt zu erstellen und zu initialisieren. Er hat denselben Namen wie die Klasse und keinen Rückgabetyp, nicht einmal `void`.
    
2. **Welche Arten von Konstruktoren gibt es?**  Es gibt drei Arten von Konstruktoren: den Standardkonstruktor (Default-Konstruktor), den parameterisierten Konstruktor und den No-Arg-Konstruktor.
    
3. **Was ist ein Standardkonstruktor?** Ein Standardkonstruktor ist ein Konstruktor ohne Parameter, der automatisch von Java erstellt wird, wenn kein anderer Konstruktor in der Klasse definiert ist. Er initialisiert Instanzvariablen auf ihre Standardwerte.
    
4. **Was ist ein No-Arg-Konstruktor?**  Ein No-Arg-Konstruktor ist ein Konstruktor mit leeren Klammern, der keine Parameter akzeptiert. Er wird verwendet, um ein Objekt ohne spezifische Initialisierung zu erstellen.
    
5. **Was ist ein parameterisierter Konstruktor?** Ein parameterisierter Konstruktor ist ein Konstruktor, der Parameter akzeptiert, um Instanzvariablen während der Objekterstellung zu initialisieren. Er ermöglicht die Übergabe von Werten beim Erstellen eines Objekts.
    
6. **Was ist der Unterschied zwischen Methode und Konstruktor?** 
    - Ein Konstruktor hat denselben Namen wie die Klasse, während eine Methode beliebige Namen haben kann.
    - Ein Konstruktor hat keinen Rückgabetyp, während eine Methode einen Rückgabetyp haben kann, der angibt, welchen Wert sie zurückgibt.
    - Ein Konstruktor wird automatisch aufgerufen, wenn ein neues Objekt erstellt wird, während eine Methode manuell aufgerufen werden muss.
    - Der Hauptzweck eines Konstruktors besteht darin, ein Objekt zu initialisieren, während eine Methode eine spezifische Aktion ausführt.

**Wichtig**: Wenn du einen Konstruktor als "private" markierst, bedeutet das, dass er nur innerhalb derselben Klasse aufgerufen werden kann. Das hat zur Folge, dass niemand außerhalb dieser Klasse ein Objekt dieser Klasse erstellen kann oder auf irgendwelche Teile der Klasse zugreifen kann.

## Strings
```java
String stringText = "This is a text";
String stringText1 = new String("This is a text");

char ch[] = {"I","b","r","a","h","i","m"};
String name = new String(ch);



```

**3. Zeichenketten-Operationen:** 
Der `String`-Datentyp bietet eine Vielzahl von Methoden, um Zeichenketten zu manipulieren und Informationen daraus zu extrahieren. Einige dieser Methoden sind:
- `length()`: Gibt die Länge der Zeichenkette zurück.
- `charAt(int index)`: Gibt das Zeichen an der angegebenen Position zurück.
- `substring(int beginIndex)`: Gibt eine Teilzeichenkette ab der angegebenen Position zurück.
- `concat(String str)`: Fügt eine Zeichenkette an eine andere Zeichenkette an.
- `toUpperCase()` und `toLowerCase()`: Ändern die Groß- und Kleinschreibung der Zeichenkette.



# Control Statements in java (Kontrollanweisungen)
Kontrollanweisungen in Java sind Anweisungen, die verwendet werden, um den Programmfluss in einem Java-Programm zu steuern. Sie ermöglichen es, Entscheidungen zu treffen, bestimmte Codeblöcke mehrmals auszuführen und verschiedene Aktionen basierend auf Bedingungen durchzuführen.

Es gibt verschiedenen Kontrollanweisungen in Java:

1. **if-Anweisung:** Die "if-Anweisung" ist eine bedingte Anweisung, die verwendet wird, um einen Codeblock auszuführen, wenn eine bestimmte Bedingung wahr (true) ist. Wenn die Bedingung nicht erfüllt ist, wird der Codeblock übersprungen.
   ```java
	int alter = 18;
	if (alter >= 18) {
	    System.out.println("Du bist volljährig.");
	}
   ```
2. **if-else-Anweisung:** Die "if-else-Anweisung" erweitert die "if-Anweisung" und ermöglicht die Ausführung eines alternativen Codeblocks, wenn die Bedingung nicht wahr ist.
   ```java
	int alter = 16;
	if (alter >= 18) {
	    System.out.println("Du bist volljährig.");
	} else {
	    System.out.println("Du bist minderjährig.");
	}
   ```   
3. **Verschachtelte if-Anweisung:** Die "verschachtelte if-Anweisung" tritt auf, wenn eine if-Anweisung innerhalb einer anderen if-Anweisung verwendet wird. Dies ermöglicht das Testen von mehreren Bedingungen in einer verschachtelten Weise.
   ```java
	int alter = 20;
	boolean führerschein = true;
	if (alter >= 18) {
	    if (führerschein) {
	        System.out.println("Du darfst Auto fahren.");
	    } else {
	        System.out.println("Du darfst noch kein Auto fahren.");
	    }
	} else {
	    System.out.println("Du bist minderjährig.");
	}
   ``` 
4. **if-else-if-Anweisung:** Die "if-else-if-Anweisung" wird verwendet, um eine Sequenz von Bedingungen zu überprüfen und den entsprechenden Codeblock auszuführen, sobald eine Bedingung wahr ist. Wenn keine der Bedingungen wahr ist, wird der Code im "else"-Block ausgeführt.
   ```java
	int note = 85;
	if (note >= 90) {
	    System.out.println("Sehr gut");
	} else if (note >= 80) {
	    System.out.println("Gut");
	} else if (note >= 70) {
	    System.out.println("Befriedigend");
	} else {
	    System.out.println("Nicht ausreichend");
	}
   ```   
5. **switch-Anweisung:** Die "switch-Anweisung" ermöglicht das Testen einer Variable gegen eine Liste von möglichen Werten. Je nachdem, welcher Wert übereinstimmt, wird der entsprechende Codeblock ausgeführt.
   ```java
	int tag = 2;
	switch (tag) {
	    case 1:
	        System.out.println("Montag");
	        break;
	    case 2:
	        System.out.println("Dienstag");
	        break;
	    // Weitere Fälle...
	    default:
	        System.out.println("Ungültiger Tag");
	}
   ```   
6. **while-Schleife:** Die "while-Schleife" wird verwendet, um einen Codeblock so lange auszuführen, wie eine bestimmte Bedingung wahr ist. Die Bedingung wird zu Beginn der Schleife überprüft.
   ```java
	int zähler = 1;
	while (zähler <= 5) {
	    System.out.println("Schleifeniteration: " + zähler);
	    zähler++;
	}
   ```   
7. **do-while-Schleife:** Die "do-while-Schleife" ist ähnlich wie die "while-Schleife", aber sie überprüft die Bedingung am Ende der Schleife. Dies bedeutet, dass der Codeblock mindestens einmal ausgeführt wird, selbst wenn die Bedingung von Anfang an falsch ist.
   ```java
	int zähler = 1;
	do {
	    System.out.println("Schleifeniteration: " + zähler);
	    zähler++;
	} while (zähler <= 5);
   ```   
8. **for-Schleife:** Die "for-Schleife" ermöglicht es, einen Codeblock eine bestimmte Anzahl von Malen auszuführen. Sie enthält eine Initialisierung, eine Bedingung und eine Aktualisierung.
   ```java
	for (int i = 1; i <= 5; i++) {
	    System.out.println("Schleifeniteration: " + i);
	}
   ```   
9. **Erweiterte for-Schleife:** Die "erweiterte for-Schleife" wird verwendet, um über Elemente einer Sammlung (z. B. Arrays oder Listen) zu iterieren, ohne die Indizes manuell zu verwalten.
   ```java
	int[] zahlen = {1, 2, 3, 4, 5};
	for (int zahl : zahlen) {
	    System.out.println("Zahl: " + zahl);
	}
   ```

### (Unlabeled) Continue Schlüsselwort 
Die `continue`-Anweisung wird verwendet, um den aktuellen Schleifendurchlauf zu überspringen und zum nächsten Durchlauf zu springen, basierend auf einer bestimmten Bedingung. Wenn `continue` ausgeführt wird, werden alle nachfolgenden Anweisungen im aktuellen Schleifendurchlauf übersprungen, und die Schleife wird mit dem nächsten Durchlauf fortgesetzt.
```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        break; // Beendet die Schleife, wenn i gleich 3 ist
    }
    System.out.println("Schleifeniteration: " + i);
}
```
### (Labeled) Continue Schlüsselwort 
In Java ermöglicht das "labeled continue" die Verwendung eines Bezeichners (Labels) zusammen mit der `continue`-Anweisung, um den Durchlauf einer äußeren Schleife in verschachtelten Schleifen zu steuern. Mit einem "labeled continue" können Sie jedoch gezielt den Durchlauf einer äußeren Schleife überspringen.
```java
outerLoop: for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 3; j++) {
        if (i == 2 && j == 2) {
            continue outerLoop; // Überspringt den gesamten Durchlauf der äußeren Schleife
        }
        System.out.println("i = " + i + ", j = " + j);
    }
}
```
### (labeled) break Schlüsselwort 
In Java ermöglicht das "labeled break" die Verwendung eines Bezeichners (Labels) zusammen mit der `break`-Anweisung, um eine äußere Schleife in verschachtelten Schleifen vorzeitig zu beenden. Normalerweise wird `break` verwendet, um die innere Schleife zu beenden und den Code nach der Schleife auszuführen. Mit einem "labeled break" können Sie jedoch gezielt den Durchlauf einer äußeren Schleife beenden.
```java
outerLoop: for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 3; j++) {
        if (i == 2 && j == 2) {
            break outerLoop; // Beendet den gesamten Durchlauf der äußeren Schleife
        }
        System.out.println("i = " + i + ", j = " + j);
    }
}
```

## Kommentare
1. Einzeilige Kommentare
2. Mehrzeilige Kommentare
3. Dokumentationskommentare (JavaDoc)
   Diese speziellen Kommentare werden verwendet, um automatisch generierte Dokumentation für Ihren Code zu erstellen. Sie beginnen mit `/**` und enden mit `*/`. JavaDoc-Kommentare werden häufig für Klassen, Methoden und Felder verwendet und enthalten Informationen über deren Verwendung und Zweck.
```java
   /**
	 * Diese Klasse repräsentiert eine Person mit Namen und Alter.
	 */
	public class Person {
	    private String name;
	    private int alter;
	
	    /**
	     * Konstruktor für die Person-Klasse.
	     * @author Habibi
	     * @param name Der Name der Person.
	     * @param alter Das Alter der Person.
	     */
	    public Person(String name, int alter) {
	        this.name = name;
	        this.alter = alter;
	    }
	
	    /**
	     * Gibt den Namen der Person zurück.
	     * @return Der Name der Person.
	     */
	    public String getName() {
	        return name;
	    }
	}
```

## system properties in java (Systemeigenschaften)
In Java sind Systemeigenschaften (System Properties) eine Möglichkeit, Informationen über das Betriebssystem und die Java-Laufzeitumgebung (JRE) abzurufen und festzulegen. Sie stellen eine Schnittstelle zwischen Ihrer Java-Anwendung und dem Betriebssystem dar und ermöglichen es Ihnen, auf Systeminformationen zuzugreifen.

Java-Codebeispiel, der alle möglichen Systemeigenschaften ausgibt:
```java
import java.util.Properties;

public class AllSystemProperties {
    public static void main(String[] args) {
        Properties properties = System.getProperties();
        properties.forEach((key, value) -> {
            System.out.println(key + ": " + value);
        });
    }
}
```

Um Systemeigenschaften in Java zu lesen und festzulegen, können Sie die
- `System.getProperty()`-Methode zum Lesen von Eigenschaften und die
```java
String javaVersion = System.getProperty("java.version");
System.out.println("Java-Version: " + javaVersion);
```
- `System.setProperty()`-Methode zum Festlegen von Eigenschaften verwenden
```java
System.setProperty("my.custom.property", "Hello, World!");
System.setProperty("author.firstname", "Habibi");
```

## Command Line arguments in java
**Command-Line-Argumente** in Java sind Werte, die Sie Ihrer Java-Anwendung beim Start über die Befehlszeile übergeben können. Diese Argumente ermöglichen es Ihrer Anwendung, benutzerspezifische Einstellungen oder Daten zu erhalten, ohne dass Änderungen im Quellcode erforderlich sind. Sie sind eine Möglichkeit, externe Konfigurationen an Ihre Anwendung zu übergeben.
### Beispiel-1
```java
public class CommandLineArgumentsExample {
    public static void main(String[] args) {
        // Überprüfen, ob Argumente übergeben wurden
        if (args.length > 0) {
            System.out.println("Anzahl der Argumente: " + args.length);

            // Ausgabe aller übergebenen Argumente
            System.out.println("Übergebene Argumente:");
            for (int i = 0; i < args.length; i++) {
                System.out.println("Argument " + i + ": " + args[i]);
            }
        } else {
            System.out.println("Keine Argumente übergeben.");
        }
    }
}
```

```
java CommandLineArgumentsExample Argument1 Argument2 Argument3
```
### Beispiel-2
```java
public class Calculator {
    public static void main(String[] args) {
        if (args.length != 2) {
            System.out.println("Bitte geben Sie zwei Zahlen als Argumente ein.");
            return;
        }

        try {
            double num1 = Double.parseDouble(args[0]);
            double num2 = Double.parseDouble(args[1]);
            double sum = num1 + num2;

            System.out.println("Summe: " + sum);
        } catch (NumberFormatException e) {
            System.out.println("Ungültige Eingabe. Bitte geben Sie gültige Zahlen ein.");
        }
    }
}
```
### Beispiel-3
```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class FileReaderExample {
    public static void main(String[] args) {
        if (args.length != 1) {
            System.out.println("Bitte geben Sie den Dateinamen als Argument ein.");
            return;
        }

        String fileName = args[0];

        try (BufferedReader reader = new BufferedReader(new FileReader(fileName))) {
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("Fehler beim Lesen der Datei: " + e.getMessage());
        }
    }
}
```

## #### main method explanation
Sie ist die erste Methode, die aufgerufen wird, wenn ein Java-Programm gestartet wird, und sie ist erforderlich, damit das Programm ausgeführt werden kann

**Methodensignatur:** Die `main`-Methode hat eine festgelegte Signatur, die strikt befolgt werden muss. Die Signatur sieht folgendermaßen aus:
```
public static void main(String[] args)
```
- `public`: Dies ist ein Zugriffsmodifikator, der angibt, dass die Methode öffentlich sichtbar ist und von außerhalb der Klasse aufgerufen werden kann.
- `static`: Dieses Schlüsselwort gibt an, dass die Methode auf Klassenebene existiert und nicht an eine Instanz der Klasse gebunden ist. Dies ermöglicht den Aufruf der Methode, ohne eine Instanz der Klasse zu erstellen.
- `void`: Dieser Rückgabetyp gibt an, dass die `main`-Methode keinen Wert zurückgibt.
- `main`: Dies ist der Name der Methode.
- `(String[] args)`: Dies sind die Parameter, die die Methode akzeptiert. In diesem Fall handelt es sich um ein Array von Zeichenketten (Strings), das häufig als `args` bezeichnet wird. Es ermöglicht, Argumente von der Befehlszeile an das Programm zu übergeben.

## Scanner
```java
import java.util.Scanner;
//
Scanner scanner = new Scanner(System.in);

scanner.next()
```
- `nextInt()`: Lesen einer Ganzzahl.
- `nextDouble()`: Lesen einer Dezimalzahl.
- `nextLine()`: Lesen einer Zeichenkette (ganze Zeile).
- `nextBoolean()`: Lesen eines booleschen Wertes (true oder false).

### #### Scanner Class in Java to Read Data from Text File
```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class ReadFileExample {
    public static void main(String[] args) {
        try {
            Scanner fileScanner = new Scanner(new File("daten.txt"));

            while (fileScanner.hasNextLine()) {
                String line = fileScanner.nextLine();
                System.out.println("Gelesene Zeile: " + line);
            }

            fileScanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("Datei nicht gefunden: " + e.getMessage());
        }
    }
}
```

```java
try {
    Scanner fileScanner = new Scanner(new File("dateiname.txt"));
} catch (FileNotFoundException e) {
    System.out.println("Datei nicht gefunden: " + e.getMessage());
}
```


## Rekursion
Rekursion in Java ist ein Konzept, bei dem eine Methode sich selbst aufruft, um eine Aufgabe zu lösen oder eine Operation durchzuführen.





## Buffered Reader Class to Read Data from Keyboard
### BufferedReader
Die `BufferedReader`-Klasse in Java ist eine nützliche Klasse zum Lesen von Benutzereingaben von der Tastatur oder aus anderen Eingabeströmen. Ähnlich wie Scanner Klasse für die Eingabe von Werten.

### InputStreamReader
Die `InputStreamReader`-Klasse in Java ist eine Klasse aus dem Paket `java.io`, die dazu dient, Bytes aus einem `InputStream` in Zeichen umzuwandeln. Dies ist nützlich, wenn Sie Daten aus einem Eingabestrom lesen möchten, aber die Daten als Zeichen interpretieren müssen, beispielsweise beim Lesen von Textdateien.

### FileReader
Die `FileReader`-Klasse in Java ist Teil des `java.io`-Pakets und wird verwendet, um Zeichen aus einer Textdatei zu lesen


```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class KeyboardInputExample {
    public static void main(String[] args) {
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));

        try {
            System.out.print("Geben Sie Ihren Namen ein: ");
            String name = reader.readLine();
            System.out.println("Hallo, " + name + "!");

            System.out.print("Geben Sie Ihr Alter ein: ");
            int age = Integer.parseInt(reader.readLine());
            // int age = Integer.valueOf(reader.readLine()); // another way to parse
            System.out.println("Sie sind " + age + " Jahre alt.");
        } catch (IOException e) {
            System.out.println("Fehler beim Lesen von Benutzereingaben: " + e.getMessage());
        }

        // Vergessen Sie nicht, den BufferedReader zu schließen, wenn er nicht mehr benötigt wird.
        try {
            reader.close();
        } catch (IOException e) {
            System.out.println("Fehler beim Schließen des Readers: " + e.getMessage());
        }
    }
}

```

### Buffered Reader Class to Read Data from Text File in Java
```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadTextFileExample {
    public static void main(String[] args) {
        try {
            BufferedReader reader = new BufferedReader(new FileReader("daten.txt"));
            String line;

            while ((line = reader.readLine()) != null) {
                System.out.println("Gelesene Zeile: " + line);
            }

            reader.close();
        } catch (IOException e) {
            System.out.println("Fehler beim Lesen der Datei: " + e.getMessage());
        }
    }
}
```
# Vererbung (Inheritance)
Es ermöglicht die Erstellung neuer Klassen basierend auf bereits existierenden Klassen. Dieser Prozess ermöglicht die Wiederverwendung von Code, die Erweiterung von Klassen und die Organisation von Klassen in Hierarchien.

**Syntax der Vererbung:**
```java
class Subclass extends Superclass {
    // Zusätzliche Attribute und Methoden der Subklasse
}
```
- `Subclass`: Die abgeleitete Klasse, die von der Basisklasse erbt.
- `Superclass`: Die Basisklasse, von der die Subklasse erbt.

**Vererbungsarten:** Es gibt verschiedene Arten von Vererbung in Java:
1. **Single Inheritance:** Eine Klasse kann nur von einer einzigen Klasse erben. Java unterstützt Single Inheritance.
2. **Multilevel Inheritance:** Eine Klasse kann von einer anderen Klasse erben, die wiederum von einer anderen Klasse erbt.
3. **Hierarchical Inheritance:** Mehrere Klassen erben von einer einzigen Basisklasse.
4. **Multiple Inheritance (Interface-Inheritance):** In Java können Klassen keine mehrfache Vererbung von Klassen haben, aber sie können mehrfache Vererbung von Schnittstellen (Interfaces) haben.

Beispiel: (Single Inheritance (Einfache Vererbung):)
```java
class Animal {
	public String name = "Cat";
    void eat() {
        System.out.println("Das Tier isst.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Der Hund bellt.");
    }
}

public class InheritanceExample {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.eat(); // Erbt von Animal
        System.out.print(myDog.name) // Erbt von Animal
        myDog.bark(); // Eigene Methode der Dog-Klasse
    }
}
```
Beispiel: (Multilevel Inheritance (Mehrstufige Vererbung))
```java
class Animal {
    void eat() {
        System.out.println("Das Tier isst.");
    }
}

class Mammal extends Animal {
    void run() {
        System.out.println("Das Säugetier rennt.");
    }
}

class Dog extends Mammal {
    void bark() {
        System.out.println("Der Hund bellt.");
    }
}

public class MultilevelInheritanceExample {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.eat(); // Erbt von Animal
        myDog.run(); // Erbt von Mammal
        myDog.bark(); // Eigene Methode der Dog-Klasse
    }
}
```
Beispiel: (Hierarchical Inheritance (Hierarchische Vererbung))
```java
class Animal {
    void eat() {
        System.out.println("Das Tier isst.");
    }
}

class Cat extends Animal {
    void meow() {
        System.out.println("Die Katze miaut.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Der Hund bellt.");
    }
}

public class HierarchicalInheritanceExample {
    public static void main(String[] args) {
        Cat myCat = new Cat();
        Dog myDog = new Dog();
        
        myCat.eat(); // Erbt von Animal
        myCat.meow(); // Eigene Methode der Cat-Klasse

        myDog.eat(); // Erbt von Animal
        myDog.bark(); // Eigene Methode der Dog-Klasse
    }
}
```

Beispiel: (Multiple Inheritance (Interface-Inheritance))
```java
interface Swimming {
    void swim();
}

interface Flying {
    void fly();
}

class Bird implements Swimming, Flying {
    public void swim() {
        System.out.println("Der Vogel kann schwimmen.");
    }

    public void fly() {
        System.out.println("Der Vogel kann fliegen.");
    }
}

public class MultipleInheritanceExample {
    public static void main(String[] args) {
        Bird myBird = new Bird();
        myBird.swim();
        myBird.fly();
    }
}
```
Java unterstützt keine Mehrfachvererbung von Klassen, warum?
dies ist eine bewusste Entscheidung der Java-Entwickler
1. **Diamant-Problem:** Das Hauptproblem bei der Mehrfachvererbung von Klassen ist das sogenannte "Diamant-Problem". Dies tritt auf, wenn eine abgeleitete Klasse von zwei oder mehr Basisklassen erbt, die eine gemeinsame Basisklasse haben. Wenn die abgeleitete Klasse auf eine Methode oder ein Attribut der gemeinsamen Basisklasse zugreift, ist es unklar, von welcher Basisklasse sie es erben sollte. Dies führt zu Verwirrung und Konflikten im Code.
2. **Alternative Lösung: Interfaces:** Java bietet eine Alternative zur Mehrfachvererbung von Klassen in Form von Schnittstellen (Interfaces). Eine Klasse kann mehrere Schnittstellen implementieren, um ähnliche Funktionalitäten zu erreichen, ohne die Probleme der Mehrfachvererbung von Klassen zu haben. Schnittstellen sind flexibler und erlauben es, den Code klarer zu strukturieren.

## Das Schlüsselwort "this"
Es ermöglicht, auf Instanzvariablen, Instanzmethoden und Konstruktoren innerhalb einer Klasse zuzugreifen. Es ermöglicht die Unterscheidung zwischen Instanzvariablen und lokalen Variablen oder Methodenparametern mit demselben Namen.

**1. Verwendung von "this" zur Unterscheidung von Variablen:**
In Java kann eine Klasse sowohl Instanzvariablen als auch lokale Variablen haben. Wenn eine lokale Variable denselben Namen wie eine Instanzvariable hat, kann "this" verwendet werden, um auf die Instanzvariable zuzugreifen und Verwirrungen zu vermeiden.
```java
class Person {
    String name; // Instanzvariable

    Person(String name) {
        this.name = name; // "this" verweist auf die Instanzvariable
    }

    void displayName() {
        System.out.println("Name: " + this.name);
    }
}
```

```java
class Calculator {
    int result;

    Calculator() {
        this.result = 0;
    }

    void add(int num) {
        this.result += num;
    }

    int getResult() {
        return this.result;
    }
}
```

## Das Schlüsselwort "super"
Es ermöglicht, auf Elemente der übergeordneten Klasse (Superklasse oder Basisklasse) zuzugreifen. Es ermöglicht die Unterscheidung zwischen den Elementen der aktuellen Klasse und denen der übergeordneten Klasse.

**1. Verwendung von "super" zum Zugriff auf die Konstruktoren der übergeordneten Klasse:**
```java
class Animal {
    String name;

    Animal(String name) {
        this.name = name;
    }
}

class Dog extends Animal {
    String breed;

    Dog(String name, String breed) {
        super(name); // Aufruf des Konstruktors der übergeordneten Klasse
        this.breed = breed;
    }
}
```
**2. Verwendung von "super" zum Zugriff auf übergeordnete Klasse-Member:**
```java
class Animal {
    void eat() {
        System.out.println("Das Tier isst.");
    }
}

class Dog extends Animal {
    void eat() {
        super.eat(); // Aufruf der Methode "eat" der übergeordneten Klasse
        System.out.println("Der Hund isst.");
    }
}
```
**3. Verwendung von "super" zur Unterscheidung zwischen übergeordneten und aktuellen Klassenvariablen:**
```java
class Animal {
    String name = "Tier";

    void printName() {
        System.out.println(name);
    }
}

class Dog extends Animal {
    String name = "Hund";

    void printName() {
        System.out.println(super.name); // Zugriff auf das Attribut der übergeordneten Klasse
        System.out.println(name); // Zugriff auf das Attribut der aktuellen Klasse
    }
}
```

# Abstraktion
Ein Prozess, indem irrelevante Details ausgeblendet werden und nur die relevanten Aspekte sichtbar gemacht werden. In Java wird Abstraktion durch Klassen(classes) und Schnittstellen(interfaces) erreicht

Verwendung von abstrakten Klassen in Java:
1. **Generische Konzepte:** Abstrakte Klassen repräsentieren generische Konzepte oder abstrakte Ideen. Sie werden oft verwendet, um eine gemeinsame Basis oder Vorlage für eine Gruppe von verwandten Klassen zu schaffen.
2. **Nicht instanziierbar:** Abstrakte Klassen können nicht direkt instanziiert werden, was bedeutet, dass Sie keine Objekte aus abstrakten Klassen erstellen können. Sie dienen als Vorlagen oder Baupläne für konkrete (nicht abstrakte) Unterklassen.
3. **Mitglieder:** Abstrakte Klassen können sowohl Felder/Attribute als auch Methoden enthalten. Diese Methoden können abstrakt oder konkret sein.
4. **Abstrakte Methoden:** Abstrakte Klassen können abstrakte Methoden enthalten, die keine Implementierung haben. Abstrakte Methoden werden deklariert, um von konkreten Unterklassen implementiert zu werden. Sie definieren einen Vertrag, den Unterklassen einhalten müssen.
5. **Abstrakte Schlüsselwörter:** Abstrakte Klassen und Methoden werden mit dem Schlüsselwort "abstract" deklariert. Das Schlüsselwort "abstract" gibt an, dass die Klasse oder Methode abstrakt ist und keine vollständige Implementierung bereitstellt.
```java
// Abstrakte Klasse
abstract class Shape {
    // Abstrakte Methode - muss implementiert werden!
    abstract double calculateArea();
    
    // Konkrete Methode
    void printDescription() {
        System.out.println("Dies ist eine geometrische Form.");
    }
}

// Konkrete Klasse, die von Shape erbt
class Circle extends Shape {
    double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    // Implementierung der abstrakten Methode
    double calculateArea() {
        return Math.PI * radius * radius;
    }
}

public class AbstractClassExample {
    public static void main(String[] args) {
        // Instanziierung einer Circle-Klasse
        Circle circle = new Circle(5.0);

        // Aufruf von Methoden
        double area = circle.calculateArea();
        System.out.println("Fläche des Kreises: " + area);
        circle.printDescription();
    }
}
```
# Interface
Es ermöglicht die Definition von Verträgen oder Schnittstellen, die von Klassen implementiert werden müssen.

**1. Grundlagen:**
- Ein Interface ist eine Sammlung von abstrakten Methodensignaturen, die von implementierenden Klassen definiert werden müssen.
- Interfaces dienen dazu, einen Vertrag zu definieren, den eine Klasse einhalten muss. Sie beschreiben, welche Methoden in einer Klasse verfügbar sein müssen, aber nicht, wie sie implementiert werden sollen.
- Ein Interface kann auch Konstanten (public static final Variablen) enthalten, die von implementierenden Klassen verwendet werden können.


**2. Schlüsselmerkmale von Interfaces:**
- **Abstrakte Methoden:** Alle Methoden in einem Interface sind abstrakt, dh sie haben keine Implementierung. Sie werden nur durch ihre Namen, Rückgabetypen und Parameterlisten definiert.
- **Public by Default:** Alle Methoden und Konstanten in einem Interface sind standardmäßig public, dh sie sind von außerhalb der Klasse, die das Interface implementiert, zugänglich.
- **Multiple Inheritance:** In Java können Klassen mehrere Interfaces implementieren, was die Möglichkeit bietet, mehrere Verträge in einer Klasse zu erfüllen.


**1. Definition eines Vertrags:**
Ein Interface in Java definiert einen Vertrag, den eine Klasse erfüllen muss. Dieser Vertrag besteht aus einer Liste von Methodensignaturen, die von Klassen implementiert werden müssen. Das Interface gibt vor, welche Methoden verfügbar sein müssen, ohne jedoch die Implementierung der Methoden selbst anzugeben.

**2. Abstrakte Methoden:**
Alle Methoden in einem Interface sind abstrakt, was bedeutet, dass sie keine Implementierung enthalten. Sie sind nur durch ihre Namen, Rückgabetypen und Parameterlisten definiert. Die tatsächliche Implementierung erfolgt in den Klassen, die das Interface implementieren.

**3. Öffentlichkeit von Methoden:**
Alle Methoden in einem Interface sind standardmäßig öffentlich (public). Dies bedeutet, dass sie von außerhalb der Klasse, die das Interface implementiert, aufgerufen werden können.

**4. Verwendung des interface-Schlüsselworts:**
Um ein Interface in Java zu erstellen, verwenden Sie das Schlüsselwort "interface" gefolgt vom Namen des Interfaces. Zum Beispiel: `interface Drawable`. Dies definiert das Interface "Drawable".

**5. Implementierung von Interfaces:**
Um ein Interface in einer Klasse zu implementieren, verwenden Sie das Schlüsselwort "implements" gefolgt vom Namen des Interfaces. Zum Beispiel: `class Circle implements Drawable`. Die Klasse "Circle" muss nun alle Methoden des Interfaces "Drawable" implementieren.

**6. Mehrfache Vererbung:**
In Java können Klassen keine mehrfache Vererbung von Klassen haben, aber sie können mehrfache Vererbung von Schnittstellen (Interfaces) haben. Das bedeutet, dass eine Klasse mehrere Interfaces implementieren kann, um verschiedene Verträge zu erfüllen.

**7. Erweiterung von Interfaces:**
Ein Interface kann ein anderes Interface erweitern (extending). Dies ermöglicht die Definition von Unterverträgen. Eine Klasse, die ein erweitertes Interface implementiert, muss sowohl die Methoden des Hauptinterfaces als auch die Methoden des erweiterten Interfaces implementieren.

```java
// Ein einfaches Interface "Drawable" zur Darstellung zeichenbarer Objekte
interface Drawable {
    void draw(); // Abstrakte Methode zur Zeichnung
    int getArea(); // Eine weitere abstrakte Methode zur Flächenberechnung
}

// Eine Klasse "Circle", die das Interface "Drawable" implementiert
class Circle implements Drawable {
    int radius;

    Circle(int radius) {
        this.radius = radius;
    }

    // Implementierung der abstrakten Methoden aus dem Interface
    public void draw() {
        System.out.println("Kreis zeichnen");
    }

    public int getArea() {
        return (int) (Math.PI * radius * radius);
    }
}

public class InterfaceExample {
    public static void main(String[] args) {
        // Instanziierung einer Circle-Klasse
        Circle circle = new Circle(5);

        // Aufruf der Methoden über das Interface
        circle.draw();
        int area = circle.getArea();
        System.out.println("Fläche des Kreises: " + area);
    }
}
```

## Hier sind die Hauptunterschiede zwischen Interfaces und abstrakten Klassen:

**1. Implementierung:**
- **Interface:** Ein Interface definiert lediglich eine Liste von abstrakten Methodensignaturen, die von Klassen implementiert werden müssen. Es enthält keine konkreten Methoden oder Felder.
- **Abstrakte Klasse:** Eine abstrakte Klasse kann sowohl abstrakte Methoden als auch konkrete Methoden (mit Implementierung) sowie Felder und Konstanten enthalten.

**2. Erweiterung:**
- **Interface:** Ein Interface kann von einer Klasse implementiert werden, indem die Klasse das Schlüsselwort "implements" verwendet.
- **Abstrakte Klasse:** Eine abstrakte Klasse kann von einer anderen Klasse erweitert werden, indem die Klasse das Schlüsselwort "extends" verwendet.

**3. Mehrfache Vererbung:**
- **Interface:** Eine Klasse kann mehrere Interfaces implementieren, um verschiedene Verträge zu erfüllen. Dies ermöglicht mehrfache Vererbung von Verhalten.
- **Abstrakte Klasse:** In Java ist keine mehrfache Vererbung von Klassen möglich. Eine Klasse kann jedoch eine abstrakte Klasse erweitern und gleichzeitig ein Interface implementieren.

**4. Konkretheit:**
- **Interface:** Interfaces sind immer abstrakt und können keine konkreten (implementierten) Methoden enthalten. Alle Methoden sind abstrakt und müssen von implementierenden Klassen implementiert werden.
- **Abstrakte Klasse:** Abstrakte Klassen können sowohl abstrakte als auch konkrete Methoden enthalten. Konkrete Methoden in einer abstrakten Klasse können von abgeleiteten Klassen geerbt werden oder überschrieben werden.

**5. Zweck:**
- **Interface:** Interfaces werden verwendet, um Verträge zu definieren und sicherzustellen, dass Klassen bestimmte Methoden implementieren. Sie ermöglichen auch die Implementierung von Polymorphismus.
- **Abstrakte Klasse:** Abstrakte Klassen werden verwendet, um gemeinsame Teile der Implementierung zwischen verwandten Klassen zu teilen. Sie dienen als Vorlagen für konkrete Klassen.

# Polymorphismus
Es bezieht sich auf die Fähigkeit eines Objekts, in verschiedenen Formen zu existieren oder in verschiedenen Kontexten verwendet zu werden. In Java wird Polymorphismus durch Vererbung und das Verhalten von Objekten erreicht.

**2. Typen von Polymorphismus in Java:**
- **Compile-Time Polymorphism (statische Polymorphie /Method Overloading):** Dies tritt während der Kompilierung auf und bezieht sich auf die Überladung von Methoden. Überladung tritt auf, wenn mehrere Methoden in derselben Klasse denselben Namen haben, sich jedoch in der Anzahl oder Art der Parameter unterscheiden. Der Compiler entscheidet, welche Methode aufgerufen wird, basierend auf den Argumenten im Aufruf.
    
- **Run-Time Polymorphism (dynamische Polymorphie /Method Overriding):** Dies tritt während der Laufzeit auf und bezieht sich auf die Überschreibung von Methoden. Überschreibung tritt auf, wenn eine abgeleitete Klasse eine Methode implementiert, die bereits in ihrer Basisklasse (oder einem implementierten Interface) definiert ist. Bei der Ausführung wird die Methode der abgeleiteten Klasse aufgerufen.

```java
class Shape {
    void draw() {
        System.out.println("Zeichne eine Form");
    }
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Zeichne einen Kreis");
    }
}

class Square extends Shape {
    @Override
    void draw() {
        System.out.println("Zeichne ein Quadrat");
    }
}

public class PolymorphismExample {
    public static void main(String[] args) {
        Shape shape1 = new Circle();
        Shape shape2 = new Square();

        shape1.draw(); // Ruft die Methode "draw" von Circle auf
        shape2.draw(); // Ruft die Methode "draw" von Square auf
    }
}
```

### Methodenüberladung (Method Overloading)
Es ermöglicht, mehrere Methoden mit demselben Namen in einer Klasse zu erstellen, solange sich ihre Parameterlisten unterscheiden. Die Methodenüberladung basiert auf der Unterscheidung der Parameterliste (Anzahl oder Typen von Parametern) einer Methode. Die Parameterliste einer Methode wird als Signatur bezeichnet.
```java
public class Calculator {
    
    // Überladen der Methode "add" für verschiedene Datentypen
    int add(int a, int b) {
        return a + b;
    }
    
    double add(double a, double b) {
        return a + b;
    }
    
    // Überladen der Methode "add" für eine unterschiedliche Anzahl von Parametern
    int add(int a, int b, int c) {
        return a + b + c;
    }
    
    // Überladen der Methode "add" mit unterschiedlichen Parametertypen
    String add(String a, String b) {
        return a + b;
    }
    
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        
        System.out.println("Summe (int): " + calc.add(5, 10));
        System.out.println("Summe (double): " + calc.add(3.5, 2.7));
        System.out.println("Summe (int): " + calc.add(2, 4, 6));
        System.out.println("Verkettung (String): " + calc.add("Hallo, ", "Welt!"));
    }
}
```

### Methodenüberschreibung (Method Overriding)
Es ermöglicht einer abgeleiteten Klasse, eine Methode aus ihrer Basisklasse neu zu definieren oder zu überschreiben. Die neu definierte Methode in der abgeleiteten Klasse hat denselben Namen, dieselben Parameter und denselben Rückgabetyp wie die Methode in der Basisklasse.

Methodenüberschreibung basiert auf der Vererbung von Klassen. In Java können Sie eine Methode in einer Basisklasse (auch Superklasse genannt) definieren, und dann kann eine abgeleitete Klasse (auch Unterklasse genannt) diese Methode überschreiben. Die Methode in der abgeleiteten Klasse wird dann anstelle der Methode in der Basisklasse aufgerufen, wenn auf ein Objekt der abgeleiteten Klasse zugegriffen wird.

```java
class Animal {
    void makeSound() {
        System.out.println("Tiere machen Geräusche");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Der Hund bellt");
    }
}

public class MethodOverridingExample {
    public static void main(String[] args) {
        Animal myAnimal = new Animal();
        Animal myDog = new Dog();

        myAnimal.makeSound(); // Ruft die Methode der Basisklasse auf
        myDog.makeSound();    // Ruft die überschriebene Methode der abgeleiteten Klasse auf
    }
}
```

### Unterschiede zwischen Method Overloading und Method Overriding
**1. Definition:**
- **Method Overloading (Methodenüberladung):** Bei der Methodenüberladung erstellen Sie mehrere Methoden in derselben Klasse mit demselben Namen, aber unterschiedlichen Parametern (Anzahl oder Typ). Die Methode wird aufgrund der unterschiedlichen Parameterlisten während der Kompilierung aufgerufen.
- **Method Overriding (Methodenüberschreibung):** Bei der Methodenüberschreibung erstellen Sie eine Methode in einer abgeleiteten Klasse, die denselben Namen, dieselbe Parameterliste und denselben Rückgabetyp wie eine Methode in der Basisklasse hat. Die Methode in der abgeleiteten Klasse ersetzt die Methode in der Basisklasse und wird zur Laufzeit aufgerufen.

**2. Entscheidungszeitpunkt:**
- **Method Overloading:** Die Entscheidung darüber, welche Methode während der Kompilierung aufgerufen wird, erfolgt aufgrund der Parameterliste (statische Bindung). Dies wird auch als Compile-Time Polymorphism (statischer Polymorphismus) bezeichnet.
- **Method Overriding:** Die Entscheidung darüber, welche Methode zur Laufzeit aufgerufen wird, erfolgt aufgrund des tatsächlichen Typs des Objekts (dynamische Bindung). Dies wird auch als Run-Time Polymorphism (dynamischer Polymorphismus) bezeichnet.

**3. Ziel und Verwendung:**
- **Method Overloading:** Das Hauptziel der Methodenüberladung besteht darin, verschiedene Versionen derselben Methode bereitzustellen, um unterschiedliche Parameter oder Parameterkombinationen zu unterstützen. Dies verbessert die Benutzerfreundlichkeit und Lesbarkeit des Codes.
- **Method Overriding:** Das Hauptziel der Methodenüberschreibung besteht darin, das Verhalten einer Methode in einer abgeleiteten Klasse anzupassen, um spezifische Anforderungen oder Funktionalitäten zu implementieren, die von der Basisklasse abweichen können. Dies ermöglicht die Erweiterung oder Anpassung des Verhaltens von Klassen.

**4. Erzeugung von Objekten:**
- **Method Overloading:** Methodenüberladung kann auf einer Klasse angewendet werden, ohne dass eine Vererbungshierarchie vorhanden ist. Die Methoden werden direkt auf Objekten dieser Klasse aufgerufen.
- **Method Overriding:** Methodenüberschreibung erfordert eine Vererbungshierarchie mit einer Basisklasse und einer abgeleiteten Klasse. Die Methode in der abgeleiteten Klasse wird auf Objekten der abgeleiteten Klasse oder deren Unterklassen aufgerufen.

**5. Rückgabetyp:**
- **Method Overloading:** Der Rückgabetyp einer überladenen Methode kann gleich sein oder sich unterscheiden. Der Rückgabetyp wird bei der Überladung nicht berücksichtigt.
- **Method Overriding:** Der Rückgabetyp der überschriebenen Methode muss identisch oder ein Subtyp des Rückgabetyps der Methode in der Basisklasse sein. Eine Änderung des Rückgabetyps ist nicht erlaubt.

```java
class Animal {
    void makeSound() {
        System.out.println("Tiere machen Geräusche");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Der Hund bellt");
    }
    
    void makeSound(String sound) {
        System.out.println("Der Hund macht " + sound);
    }
}

public class Example {
    public static void main(String[] args) {
        Animal animal = new Animal();
        Animal dog = new Dog();
        Dog myDog = new Dog();

        animal.makeSound();      // Aufruf der Methode in Animal
        dog.makeSound();         // Aufruf der überschriebenen Methode in Dog
        myDog.makeSound();       // Aufruf der überschriebenen Methode in Dog
        myDog.makeSound("Wuff"); // Aufruf der überladenen Methode in Dog
    }
}

```

# "final" Schlüsselwort
Das Hinzufügen des "final"-Modifikators zu einem Element hat verschiedene Auswirkungen und Einschränkungen, die je nach dem Elementtyp variieren.

**1. Final für Klassen:**
- Wenn Sie eine Klasse mit dem "final"-Modifikator deklarieren, bedeutet dies, dass diese Klasse nicht von anderen Klassen abgeleitet werden kann. Sie ist endgültig und kann nicht als Basisklasse verwendet werden. Zum Beispiel:
```java
final class MyFinalClass {
    // ...
}
```

**2. Final für Methoden:**
- Wenn Sie eine Methode mit dem "final"-Modifikator deklarieren, bedeutet dies, dass die Methode in abgeleiteten Klassen nicht überschrieben werden kann. Die Methode ist endgültig und behält ihre Implementierung bei. Zum Beispiel:
```java
class MyBaseClass {
    final void myFinalMethod() {
        // Diese Methode kann nicht in abgeleiteten Klassen überschrieben werden
    }
}
```

**3. Final für Variablen (Konstanten):**
- Wenn Sie eine Variable mit dem "final"-Modifikator deklarieren, bedeutet dies, dass die Variable nur einmal zugewiesen werden kann. Sie wird zu einer Konstanten und muss sofort oder im Konstruktor initialisiert werden. Zum Beispiel:
```java
final int myConstant = 42;
```

**4. Final für Referenzen:**
- Wenn Sie eine Referenzvariable mit dem "final"-Modifikator deklarieren, bedeutet dies, dass die Referenzvariable nicht neu zugewiesen werden kann. Das bedeutet jedoch nicht, dass das Objekt, auf das sie verweist, unveränderlich ist. Zum Beispiel:
```java
final MyClass myInstance = new MyClass();
```

**5. Final für Argumente:**
- Wenn Sie ein Argument in einer Methode mit dem "final"-Modifikator deklarieren, bedeutet dies, dass das Argument innerhalb der Methode nicht geändert werden kann. Zum Beispiel:
```java
void myMethod(final int x) {
    // x kann hier nicht geändert werden
}
```

Vorteile:
- Das Verwenden von "final" kann dazu beitragen, den Code sicherer zu machen, indem verhindert wird, dass bestimmte Elemente geändert oder überschrieben werden.

## Die Kapselung (Encapsulation)
Die Kapselung zielt darauf ab, den Zugriff auf Daten zu kontrollieren und die Datenintegrität zu wahren, indem sie den direkten Zugriff auf Daten von außerhalb der Klasse einschränkt.

**Getter und Setter-Methoden:** Um den Zugriff auf private Daten in einer Klasse zu ermöglichen, werden Getter- und Setter-Methoden verwendet. Getter-Methoden werden verwendet, um den Wert einer privaten Variable abzurufen, während Setter-Methoden verwendet werden, um den Wert einer privaten Variable festzulegen. Diese Methoden ermöglichen die Kontrolle und Validierung des Datenzugriffs.

```java
public class Person {
    private String name; // Private Datenfeld

    // Konstruktor
    public Person(String name) {
        this.name = name;
    }

    // Getter-Methode für das Datenfeld 'name'
    public String getName() {
        return name;
    }

    // Setter-Methode für das Datenfeld 'name'
    public void setName(String name) {
        if (name != null && !name.isEmpty()) {
            this.name = name;
        }
    }
}
```

# Die Fehlerbehandlung (Exception Handling)
Die Fehlerbehandlung (Exception Handling) in Java ist ein wichtiger Mechanismus, um mit unerwarteten oder fehlerhaften Situationen während der Programmausführung umzugehen.

- **try-catch-Blöcke:** Mit einem `try`-Block können Sie Code schreiben, der Ausnahmen auslösen könnte. In einem `catch`-Block können Sie festlegen, wie mit der Ausnahme umgegangen werden soll. Ein `finally`-Block kann verwendet werden, um Code auszuführen, der unabhängig davon, ob eine Ausnahme aufgetreten ist oder nicht, ausgeführt werden soll.
- **throws-Klausel:** In Methodendeklarationen können Sie die `throws`-Klausel verwenden, um anzuzeigen, dass eine Methode eine bestimmte Ausnahme auslösen könnte. Die aufrufende Methode muss dann die Ausnahme behandeln oder selbst deklarieren, dass sie die Ausnahme weitergibt.
  
```java
public class ExceptionHandlingExample {
    public static void main(String[] args) {
        try {
            int result = divide(10, 0);
            System.out.println("Ergebnis: " + result);
        } catch (ArithmeticException e) {
            System.err.println("Fehler: Division durch Null.");
        }
    }

    public static int divide(int a, int b) {
        return a / b;
    }
}
```

## Standard-Fehlerbehandlung (Default Exception Handling)
Die Standard-Fehlerbehandlung (Default Exception Handling) in Java tritt auf, wenn Sie in Ihrem Code keine spezielle Fehlerbehandlung für eine Ausnahme (Exception) implementieren. Wenn keine spezielle Behandlung für eine Ausnahme angegeben ist, wird die Ausnahme normalerweise an die aufrufende Methode oder an das JVM (Java Virtual Machine) zurückgegeben, wo sie standardmäßig behandelt wird

## Ausnahmen (Exceptions) und Fehler (Errors)
- Ausnahmen können aufgrund von Fehlern im Programmcode auftreten, wie z.B. eine Division durch Null, ein ungültiger Dateipfad oder das Öffnen einer Datei, die nicht existiert.
- Ausnahmen erben von der Klasse `Exception` oder ihren Unterklassen und werden oft als "überprüfbare Ausnahmen" bezeichnet. Das bedeutet, dass der Compiler Entwickler dazu zwingt, Ausnahmen entweder zu behandeln (mit `try-catch`) oder in der Methode-Deklaration mit `throws` weiterzugeben.
- Beispiele für Ausnahmen sind `IOException`, `ClassNotFoundException` und `NullPointerException`.


- Fehler treten normalerweise aufgrund von Problemen auf, die das Programm nicht beeinflussen kann, wie z.B. schwerwiegender Speichermangel, Hardwarefehler oder JVM-Probleme.
- Fehler erben von der Klasse `Error` oder ihren Unterklassen und werden als "unerwartete Fehler" bezeichnet. Entwickler sollten normalerweise keine Versuche unternehmen, Fehler zu behandeln oder weiterzugeben, da dies normalerweise nicht sinnvoll ist.
- Beispiele für Fehler sind `OutOfMemoryError`, `StackOverflowError` und `VirtualMachineError`.

### Die Exception-Hierarchie in Java

```
Object
|
Throwable
|--- Error
|   |--- AssertionError
|   |--- LinkageError
|   |   |--- ClassCircularityError
|   |   |--- ClassFormatError
|   |   |--- ...
|   |--- VirtualMachineError
|       |--- OutOfMemoryError
|       |--- StackOverflowError
|       |--- ...
|
|--- Exception
|   |--- RuntimeException
|   |   |--- ArithmeticException
|   |   |--- NullPointerException
|   |   |--- IndexOutOfBoundsException
|   |   |   |--- ArrayIndexOutOfBoundsException
|   |   |   |--- StringIndexOutOfBoundsException
|   |   |--- ...
|   |--- IOException
|   |   |--- FileNotFoundException
|   |   |--- EOFException
|   |   |--- ...
|   |--- ...
|--- ...

```
**1. Object (Objekt):** Alle Klassen in Java erben direkt oder indirekt von der Klasse `Object`, einschließlich der Ausnahme-Klassen. `Object` ist die Wurzelklasse der Java-Klassenhierarchie.

**2. Throwable (Werfbar):** `Throwable` ist die direkte Superklasse für alle Ausnahme- und Fehlerklassen in Java. Sie ist eine abstrakte Klasse und definiert zwei Hauptmethoden: `getMessage()` und `printStackTrace()`. `Throwable` hat zwei direkte Unterklassen: `Error` und `Exception`.

 **3. Exception (Ausnahme):** Diese Klasse ist die Superklasse für alle Ausnahmen, die behandelt oder vermieden werden können. Innerhalb dieses Zweigs gibt es zwei Hauptzweige:
	 - **Checked Exceptions (überprüfbare Ausnahmen):** Diese Ausnahmen müssen behandelt oder weitergegeben werden. Beispiele sind `IOException` und `SQLException`.
    - **Unchecked Exceptions (unerwartete Ausnahmen):** Diese Ausnahmen können behandelt werden, müssen es aber nicht. Sie treten normalerweise aufgrund von Programmierfehlern auf. Beispiele sind `NullPointerException` und `ArithmeticException`.














