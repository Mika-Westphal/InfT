# Rechtschreib fehler möglich, da dieser Text mit extremer Crunsh Time geschrieben wurde!

# BIOS
Das BIOS (Basic Input Output System) ist die Firmware des <LINK INTERN Mainboard>Mainboards</LINK>, welche aufgaben wie z.B. die Hardware Initialisierung oder die bereitstellung von Runtime Services (Siehe unten für weitere Informationen) für das OS und deren Programme übernimmt. Ein BIOS ist eigentlich auf jedem Geräten zu finden wo der Entwickler die Hardware Initialisierung selber übernimmt. Geräte bei denen dies nicht der Fall ist sind z.B. der 6502 (Die CPU der NES oder des C64) oder der Ricoh 5A22 aus der SNES.

## Abhänigkeiten
Damit das BIOS funktioniert, wird die CPU und der RAM benötigt. Eine GPU wird nicht zwingend benötigt, da die gesammten ausgaben, wenn überhaupt benötigt, auch z.B. über eine <LINK INTERN Serielle Schnittstelle>Serielle Schnittstelle</LINK> ausgegeben werden können. Allerdings muss das BIOS dafür speziell entwickelt werden, da die BIOS's die auf nomalen <LINK INTERN Mainboard>Mainboards</LINK> installiert sind immer versuchen einen <LINK INTERN GPU>GPU</LINK> zu Initialisieren und sollte dies nicht Funktionieren, da z.B. da kein <LINK INTERN GPU>GPU</GPU> verbaut ist, wird das BIOS in den Fail-mode gehen, wo er dann bis zum abschalten des Computers verbleibt.

## User Interface
Das User Interface des BIOS ist eine Text Basierte oberfläche, welche zur Konfiguration oder überprüfung der Hardware dient. Allerdings besitzt nicht jedes BIOS so ein User Interface. Denn z.B. bei der PS4 oder der Nintendo Switch besitzt das BIOS kein User Interface oder jegliche, für den nutzer ersichtlichen, ausgaben.

## Runtime Services
Runtime Services sind funktionen die das BIOS dem OS sowie deren Programmen zur verfügung stellt. Diese übernehmen aufgaben wie z.B. das ansprechen der Netzwerk Schnittstelle, Keyboard Input oder Speicher Operationen. Diese dienen zur Standartisierung von solchen Aufgaben welche die Kompatiblität erhöht, da das Programm auf nicht oder nur minimal angepasst werden muss wenn es auf einem AMD statt Intel CPU läuft.

### Overclocking
Das Overcloking, oder auch Übertackten gennant, ist das verändern der Hardware eigenschaften, welche die Leistung beeinflussen. Damit dies Funktioniert muss das <LINK INTERN Mainboard>Mainboard</LINK> sowie die Komponenten diese eigenschaft auch Unterstützen. Übertaktet werden zurzeit eigentlich nur die <LINK INTERN CPU>CPU</LINK>, <LINK INTERN GPU>GPU</LINK>, <LINK INTERN RAM>RAM</LINK> und in manchen fällen auch der <LINK INTERN Monitor>Monitor</LINK>. Hierbei ist das Overclocking komplett aus dem OS heraus durchführbar, wofür allerdings das BIOS dies Unterstützen muss, sowie spezielle Programme benötigt werden, wie z.B. für RAM und CPU AMD Ryzen Master <IMG bios_0006.png>, für die GPU MSI Afterburner <IMG bios_0005.png> oder für den Monitor das NVIDIA Controle Panel vom Treiber <IMG bios_0007.png>.

#### CPU
Um die CPU zu übertackten muss die <LINK INTERN CPU>CPU</LINK> dies auch Unterstützen. In denn meisten fällen wird die Übertacktung durch die Blockierung des Multiplikator's der Frequenz verhindert. Sollte diese allerdings freigegeben sein, so kann man diesen ändern. Dieser kann sowohl nach oben als auch nach unten verändert werden. Wenn der Wert nach unten verändert wird, veringert man die Taktrate der CPU. Dies hat den Vorteil, dass die CPU nun weniger Strom benötigt und weniger Hitze produziert. Es ist auch möglich die Taktrate selbst zu verändern, was allerdings nicht so oft gemacht wird. Sollte allerdings die Taktrate nach oben angepasst werden, so benötgt die CPU mehr Strom, produziert mehr wärme und die Wahrscheinlichkeit das Fehler bei den Berechnungen entstehen steigen. Die CPU bekommt allerdings nicht automatisch mehr Strom, weshalb man ab einen gewissen Punkt auch die Spannung anheben muss, was zu einem Defekt der <LINK INTERN CPU>CPU</LINK> und/oder des <LINK INTERN Mainboard>Mainboard</LINK> führen kann, sollte diese zu stark angehoben werden. 
Die Tatsächliche Taktrate ergibt sich hierbei aus Clock * Multiplikator. Also sollte z.B. der Clock auf 100 MHz stehen und der Multiplikator auf 36 stehen so entsteht eine Tatsächliche Taktrate von 3.6 GHz. Hierbei könnte die Übertacktung wie folgt aussehen <IMG bios_0008.png></IMG>

#### RAM
Um den <LINK INTERN RAM>RAM</LINK> zu Übertackten, kann man die Taktrate und die Timings anpassen. Das übertackten des <LINK INTERN RAM>RAM's</LINK> hat im bezug auf die Spannung, den Strom und der Hitze die selben Vor- und Nachteile wie die <LINK INTERN CPU>CPU</LINK>. Allerdings müssen die RAM Timings nach oben angepasst werden, sollte die Taktrate erhöht werden. Denn wenn die Timings in Kombination mit der Taktrate nicht lang genug sein, so kann der <LINK INTERN RAM>RAM</LINK> nicht schnell genug die Aufgaben abarbeiten und es kann zu einen page fault fehler kommen, welcher das OS zum absturtz bringt.

### Boot Priorität
In dem Menu der Boot Priorität kann festgelegt werden in welcher reinfolge, von Speichermedien, dass BIOS versuchen soll das OS zu starten. Das ist so gemeint das wenn er auf dem ersten Speichermedium kein System findet er versucht von dem zweiten das System zu laden und so weiter. Kann er letzten endes garkein OS Starten so zeigen die meisten BIOS's Nachrichten wie "no boot device found" an.

### Boot Menu
Es ist ein Menu wo alle Speicher medien aufgelistet werden, wo man dann angeben soll von welchem das BIOS versuchen soll zu Starten. Klapt dies nicht, weil er z.B. nichts zum Starten findet, fängt er einfach an die Boot Priorität abzuarbeiten. Das gerät von welchem letzten endes gestartet wird, wird im <LINK INTERN RAM>RAM</RAM>

## Hardware Initialisierung und Boot
Sobald der Computer eingeschaltet wird, benötigt das <LINK INTERN Netzteil>Netzteil</LINK> eine gewisse zeit bevor es die richtige Spannung abgeben kann. Da keinerlei Werten im <LINK INTERN RAM>RAM</LINK> oder den CPU Registern stehen, weiß die CPU auch nicht wo das BIOS sich auf dem Chip befindet. Aus diesem Grund fangen die <LINK INTERN CPU>CPU's</LINK> immer bei der Initialisierung an den Code des BIOS Chip's an stelle 0xFFF0 auszuführen. Dieser ist meistens ein Jump befehl, welcher zu dem richtigen Einstigspunkt des BIOS führt. Nun wird ein "Power On Self Test" durchgeführt, welcher die Peripheriegeräte, die Festplatten, den <LINK INTERN RAM>RAM</LINK> sowie andere wichtige Hardware Initialisiert. Damit das BIOS auch weiß wie viel <LINK INTERN RAM>RAM</LINK> er zur verfügung hat setzt er das Ende des Speichers wodurch er die genaue größe erhällt. Sollte dieser Fehl schlagen stellt dies das BIOS mit hilfe von Status LED's da (Also z.B. wenn er bei dem RAM hängen bleibt läuchtet RAM), mit Biep codes oder mit Error Codes welche auf einem Zahlen Display stehen. Sollte dies aber funktioniert haben, sucht das BIOS normalerweise nach dem GPU BIOS, welches normalerweise an der Stelle 0xC000 ligt und führt dieses aus. Nachdem das GPU BIOS durch ist sucht das Mainboard BIOS nach weiteren BIOS'en, eigentlich haben die IDE/ATA Festplatten noch solch ein BIOS welches an der Stelle 0xC800 zu finden ist. Das macht er solange bis alle BIOS'se ausgeführt wurden. Dies ist der moment wo der Computer das erste mal etwas auf dem Bildschirm darstellt. Denn nun wird der Startup screen, wie z.B. ein Bild des Herstellers oder Hardware Informationen gerendert. Als nächstes versucht der Computer durch weitere Tests herauszufinden welche Hardware verbaut ist und versucht diese passend zu Konfigurieren.

# UEFI

## Abhänigkeiten

## User Interface

### Bios Update

## Hardware Initialisierung

## Boot