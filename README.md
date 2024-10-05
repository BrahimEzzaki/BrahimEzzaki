- 👋 Hi, Ich bin @Brahim Ezzaki
- 👀Ich möchte ein Program entwikeln, das den Rechner per Sprache steuert
Ich möchte ein System entwickeln, das Sprachbefehle auf meinem Computer erkennt und automatisch Programme startet oder Aufgaben ausführt. Das System sollte modular sein und die Sprachbefehle mit einem Python-Skript in Text umwandeln (ich benutze Whisper). Die folgende Architektur ist angedacht:

Module:

Spracherkennung (bereits durch Python/Whisper abgedeckt)
Befehlsanalyse: Ein C#-Programm, das Textbefehle interpretiert und Aktionen ausführt. Es sollte flexibel sein, um später Befehle einfach erweitern zu können.
Skripterstellung und -ausführung: Es soll in der Lage sein, PowerShell-Skripte zu generieren und auszuführen.
Kontrollmodul: Bevor das endgültige Skript ausgeführt wird, soll es überprüft werden, ob es dem Ziel des ursprünglichen Sprachbefehls entspricht.
Gedächtnis: Häufig verwendete Befehle sollen in einer lokalen Datenbank gespeichert werden, damit sie nicht immer neu analysiert werden müssen.
Langfristige Anforderungen:

Das System soll auf Windows laufen (C#), aber eine spätere Erweiterung für MacOS/Linux wäre wünschenswert.
Modularität ist entscheidend, um jederzeit ein Modul optimieren oder austauschen zu können.
Erste Schritte:
Ich möchte mit einer einfachen Befehlsanalyse in C# beginnen.

Zunächst reicht eine manuelle Eingabe von Befehlen über die Konsole.
Die Befehle sollen in einer commands.json-Datei gespeichert werden.
Die commands.json-Datei soll folgende Informationen enthalten:

Pattern: Ein regulärer Ausdruck zur Erkennung des Befehls.
Action: Ein eindeutiger Bezeichner für die Aktion.
Command: Das Programm oder Skript, das ausgeführt wird.
Arguments: Platzhalter für optionale Parameter.
Die JSON-Datei soll flexibel genug sein, um neue Programme und Parameter hinzuzufügen. Beispiele:

Öffnen von Notepad, Browsern oder Dateien.
Unterstützung für dynamische Parameter wie Dateinamen oder URLs.
Ein C#-Programm, das diese JSON-Datei liest, den eingegebenen Text interpretiert und dann die entsprechenden Programme mit oder ohne Argumente ausführt, sollte implementiert werden.

Befehlsmuster wie:

„öffne notepad“
„starte browser mit url https://example.com“
„öffne datei dokument.txt“ sollten unterstützt werden.

Eine visuelle Unterstützung in Kombination mit der Sprachsteuerung macht die Navigation durch das Dateisystem effizienter.
Mit Technologien wie WPF oder WinForms lässt sich eine einfache, aber effiziente Oberfläche erstellen, die sowohl Klick- als auch Sprachinteraktionen unterstützt.
Durch eine ListView oder TreeView können Ordner und Dateien klar dargestellt und einfach geöffnet werden.
Eine Breadcrumb-Navigation sorgt dafür, dass der Benutzer jederzeit weiß, wo er sich befindet, und ermöglicht eine schnelle Navigation.
