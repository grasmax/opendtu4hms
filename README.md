# opendtu4hms
Reparatur der openDTU von selbstbau-pv.de für HMS-Wechselrichter

August 2026

Seit 2024 betreibe ich eine openDTU von selbstbau-pv.de mit Hoymiles-HMS-Wechselrichtern.
Die Funkverbindung zu den Wechselrichtern ist stabil. Aber die WLAN-Verbindung zur Fritzbox (7490 und 5530) ist sehr instabil.

Diverse Optimierungen in der 5530 bei WLAN-Kanal und -Band-Einstellungen brachten keine Verbesserung.
Im Gegenteil: mehrmals verlor die openDTU alle Einstellungen einschließlich für Netzwerk und Wechselrichter.

Es mussten die Werkseinstellungen per erase/flash restauriert werden.
Leider ist die Doku https://www.opendtu.solar/firmware/webinstall/ an diesem Punkt sehr unpräzise.
Deshalb folgt ihr eine etwas verbesserte Anleitung, um eine kaputte DTU wieder in Betrieb zu nehmen.
Bei dieser Gelegenheit wurde auch das überflüssige nrf-Funkmodul entfernt, das für die Kommunikation mit ausschließlich HMS-Wechselrichtern gar nicht gebraucht wird!
<img width="403" height="265" alt="image" src="https://github.com/user-attachments/assets/bba614e4-5544-4882-9a0a-6da2830e6722" />
