# opendtu4hms
Reparatur der openDTU von selbstbau-pv.de für HMS-Wechselrichter

August 2026 / 35W-Netzteil /FritzRepeater 600/ Fritzbox 5530 / Windows10-PC mit aktueller ESU-Version /HMS2000

Seit 2024 betreibe ich eine openDTU von selbstbau-pv.de mit Hoymiles-HMS-Wechselrichtern.
Die Funkverbindung zu den Wechselrichtern ist stabil. Aber die WLAN-Verbindung zur Fritzbox (7490 und 5530) ist sehr instabil.

Diverse Optimierungen in der 5530 bei WLAN-Kanal und -Band-Einstellungen brachten keine Verbesserung.
Im Gegenteil: mehrmals verlor die openDTU alle Einstellungen einschließlich für Netzwerk und Wechselrichter.

Es mussten die Werkseinstellungen per erase/flash restauriert werden.
Leider ist die Doku https://www.opendtu.solar/firmware/webinstall/ an diesem Punkt sehr unpräzise.
Deshalb folgt ihr eine etwas verbesserte Anleitung, um eine kaputte DTU wieder in Betrieb zu nehmen.
Bei dieser Gelegenheit wurde auch das überflüssige nrf-Funkmodul entfernt, das für die Kommunikation mit ausschließlich HMS-Wechselrichtern gar nicht gebraucht wird!
<img width="403" height="265" alt="image" src="https://github.com/user-attachments/assets/bba614e4-5544-4882-9a0a-6da2830e6722" />

Unbedingt zu beachten:
- Im stromlosen Zustand das NRF-Funkmodul ausbauen.
- Die DTU mit einem USB-Kabel mit dem PC verbinden. Einen usb3-Port verwenden! Keinen Hub dazwischen und keinen usb2-Port!
- den boot-Knopf unbedingt vor dem Anstecken des Kabels drücken und nach dem Anstecken loslassen! <img width="287" height="175" alt="image" src="https://github.com/user-attachments/assets/cc361f6c-5f84-46f9-82ca-50f4c4cd53d5" />

Dann den webflasher starten: https://www.opendtu.solar/firmware/webinstall/

Unbedingt "ESP32" auswählen und "INSTALL" drücken.

<img width="527" height="485" alt="image" src="https://github.com/user-attachments/assets/47416fbf-8915-4309-9111-1cc2c22984f9" />

"CP2102..." auswählen und "Verbinden"

Dann "INSTALL OPENDTU..."

<img width="332" height="170" alt="image" src="https://github.com/user-attachments/assets/374712fa-caad-43a3-9a83-49b9b15ce209" />

Dann sollte die Neuinstallation beginnen mit "Erasing", dann "Installing".
Bei 63% bleibt die Sanduhr kurz hängen und springt dann auf 100%. Nach "Warapping" erscheint die Erfolgsmeldung.

Um sich mit den HMS-Wechselrichtern verbinden zu können und das nrf-Modul abzuschalten, muss nun noch die korrigierte! pin-Datei (siehe Anlage) eingespielt werden:

<img width="1191" height="525" alt="image" src="https://github.com/user-attachments/assets/1de63312-8cf9-4a31-9a94-167e8de89dd7" />

Dann kann auch das Harwareprofil für hms ausgewählt werden:

<img width="778" height="351" alt="image" src="https://github.com/user-attachments/assets/84f1600e-15bf-4fbb-ab74-6204210fd578" />

Vor dem Neustart (Strom aus/ein) muss die Antenne wieder angeschraubt und es müssen alle Einstellungen vorgenommen werden:
- neues DTU-Passwort
- Netzwerk ssid und passwort
- DTU Sendeleistung und -Intervall
- MQTT und Broker-IP
- alle Wechselrichter





