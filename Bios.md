# BIOS
Das BIOS (Basic Input Output System) ist die Firmware des <link INTERN Mainboard>Mainboards</link>, welche aufgaben wie z.B. die Hardware Initialisierung oder die bereitstellung von Runtime Services (Siehe unten für weitere Informationen) für das OS und deren Programme übernimmt. Ein BIOS ist eigentlich auf jedem Geräten zu finden wo der Entwickler die Hardware Initialisierung selber übernimmt. Geräte bei denen dies nicht der Fall ist sind z.B. der 6502 (Die CPU der NES oder des C64) oder der Ricoh 5A22 aus der SNES.

## Abhänigkeiten
Damit das BIOS funktioniert, wird die CPU und der RAM benötigt. Eine GPU wird nicht zwingend benötigt, da die gesammten ausgaben, wenn überhaupt benötigt, auch z.B. über eine <link INTERN Serielle Schnittstelle>Serielle Schnittstelle</link> ausgegeben werden können. Allerdings muss das BIOS dafür speziell entwickelt werden, da die BIOS's die auf nomalen <link INTERN Mainboard>Mainboards</link> installiert sind immer versuchen einen <link INTERN GPU>GPU</link> zu Initsialisieren und sollte dies nicht Funktionieren, da z.B. da kein <link INTERN GPU>GPU</GPU> verbaut ist, wird das BIOS in den Fail-mode gehen, wo er dann bis zum abschalten des Computers verbleibt.

## User Interface
Das User Interface des BIOS ist eine Text Basierte oberfläche, welche zur Konfiguration oder überprüfung der Hardware dient. Allerdings besitzt nicht jedes BIOS so ein User Interface. Denn z.B. bei der PS4 oder der Nintendo Switch besitzt das BIOS kein User Interface oder jegliche, für den nutzer ersichtlichen, ausgaben.
### Overclocking
Das Overcloking, oder auch Übertackten gennant, ist das verändern der Hardware eigenschaften, welche die Leistung beeinflussen. Damit dies Funktioniert muss das <link INTERN Mainboard>Mainboard</link> sowie die Komponenten diese eigenschaft auch Unterstützen. Übertaktet werden zurzeit eigentlich nur die <link INTERN CPU>CPU</link>, <link INTERN GPU>GPU</link>, <link INTERN RAM>RAM</link> und in manchen fällen auch der <link INTERN Monitor>Monitor</link>. Hierbei ist das Overclocking komplett aus Windows durchführbar, wofür allerdings das BIOS dies Unterstützen muss, sowie spezielle Programme benötigt werden, wie z.B. für RAM und CPU AMD Ryzen Master <img bios_0006.png>, für die GPU MSI Afterburner <img bios_0005.png> oder für den Monitor das NVIDIA Controle Panel vom Treiber.
#### CPU
Um die CPU zu übertackten muss der

#### RAM

### Boot Priorität

### Boot Menu

## Hardware Initialisierung

## Boot

# UEFI
## Aufgaben

## Abhänigkeiten

## User Interface
### Overclocking
#### CPU
##### AMD Overclocking

#### RAM

### Boot Priorität

### Boot Menu

### Bios Update

## Hardware Initialisierung
