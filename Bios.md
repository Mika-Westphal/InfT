# BIOS
Das BIOS (Basic Input Output System) ist die Firmware des <link INTERN Mainboard>Mainboards</link>, welche aufgaben wie z.B. die Hardware Initialisierung oder die bereitstellung von Runtime Services (Siehe unten für weitere Informationen) für das OS und deren Programme übernimmt. Ein BIOS ist eigentlich auf jedem Geräten zu finden wo der Entwickler die Hardware Initialisierung selber übernimmt. Geräte bei denen dies nicht der Fall ist sind z.B. der 6502 (Die CPU der NES oder des C64) oder der Ricoh 5A22 aus der SNES.

## Abhänigkeiten
Damit das BIOS funktioniert, wird die CPU und der RAM benötigt. Eine GPU wird nicht zwingend benötigt, da die gesammten ausgaben, wenn überhaupt benötigt, auch z.B. über eine <link INTERN Serielle Schnittstelle>Serielle Schnittstelle</link> ausgegeben werden können. Allerdings muss das BIOS dafür speziell entwickelt werden, da die BIOS's die auf nomalen <link INTERN Mainboard>Mainboards</link> installiert sind immer versuchen einen <link INTERN GPU>GPU</link> zu Initialisieren und sollte dies nicht Funktionieren, da z.B. da kein <link INTERN GPU>GPU</GPU> verbaut ist, wird das BIOS in den Fail-mode gehen, wo er dann bis zum abschalten des Computers verbleibt.

## User Interface
Das User Interface des BIOS ist eine Text Basierte oberfläche, welche zur Konfiguration oder überprüfung der Hardware dient. Allerdings besitzt nicht jedes BIOS so ein User Interface. Denn z.B. bei der PS4 oder der Nintendo Switch besitzt das BIOS kein User Interface oder jegliche, für den nutzer ersichtlichen, ausgaben.

### Overclocking
Das Overcloking, oder auch Übertackten gennant, ist das verändern der Hardware eigenschaften, welche die Leistung beeinflussen. Damit dies Funktioniert muss das <link INTERN Mainboard>Mainboard</link> sowie die Komponenten diese eigenschaft auch Unterstützen. Übertaktet werden zurzeit eigentlich nur die <link INTERN CPU>CPU</link>, <link INTERN GPU>GPU</link>, <link INTERN RAM>RAM</link> und in manchen fällen auch der <link INTERN Monitor>Monitor</link>. Hierbei ist das Overclocking komplett aus dem OS heraus durchführbar, wofür allerdings das BIOS dies Unterstützen muss, sowie spezielle Programme benötigt werden, wie z.B. für RAM und CPU AMD Ryzen Master <img bios_0006.png>, für die GPU MSI Afterburner <img bios_0005.png> oder für den Monitor das NVIDIA Controle Panel vom Treiber <img bios_0007.png>.

#### CPU
Um die CPU zu übertackten muss die <link INTERN CPU>CPU</link> dies auch Unterstützen. In denn meisten fällen wird die Übertacktung durch die Blockierung des Multiplikator's der Frequenz verhindert. Sollte diese allerdings freigegeben sein, so kann man diesen ändern. Dieser kann sowohl nach oben als auch nach unten verändert werden. Wenn der Wert nach unten verändert wird, veringert man die Taktrate der CPU. Dies hat den Vorteil, dass die CPU nun weniger Strom benötigt und weniger Hitze produziert. Es ist auch möglich die Taktrate selbst zu verändern, was allerdings nicht so oft gemacht wird. Sollte allerdings die Taktrate nach oben angepasst werden, so benötgt die CPU mehr Strom, produziert mehr wärme und die Wahrscheinlichkeit das Fehler bei den Berechnungen entstehen steigen. Die CPU bekommt allerdings nicht automatisch mehr Strom, weshalb man ab einen gewissen Punkt auch die Spannung anheben muss, was zu einem Defekt der <link INTERN CPU>CPU</link> und/oder des <link INTERN Mainboard>Mainboard</link> führen kann, sollte diese zu stark angehoben werden. 
Die Tatsächliche Taktrate ergibt sich hierbei aus Clock * Multiplikator. Also sollte z.B. der Clock auf 100 MHz stehen und der Multiplikator auf 36 stehen so entsteht eine Tatsächliche Taktrate von 3.6 GHz. Hierbei könnte die Übertacktung wie folgt aussehen <img bios_0008.png></img>

#### RAM
Um den <link INTERN RAM>RAM</link> zu Übertackten, kann man die Taktrate und die Timings anpassen. Das übertackten des <link INTERN RAM>RAM's</link> hat im bezug auf die Spannung, den Strom und der Hitze die selben Vor- und Nachteile wie die <link INTERN CPU>CPU</link>. Allerdings müssen die RAM Timings nach oben angepasst werden, sollte die Taktrate erhöht werden. Denn wenn die Timings in Kombination mit der Taktrate nicht lang genug sein, so kann der <link INTERN RAM>RAM</link> nicht schnell genug die Aufgaben abarbeiten und es kann zu einen page fault fehler kommen, welcher das OS zum absturtz bringt.

### Boot Priorität
In dem Menu der Boot Priorität kann festgelegt werden, in welcher reinfolge, von Massenspeicher, dass BIOS versuchen soll das OS zu laden.

### Boot Menu

## Hardware Initialisierung

## Boot

# UEFI

## Abhänigkeiten

## User Interface

### Bios Update

## Hardware Initialisierung

## Boot