# Arduino-Audio-Meter.
Arduino bidez audio seinailea neurtzeko proiektua.
![audio_meter_axo](https://user-images.githubusercontent.com/99732982/154351242-8bf0f556-74bf-4261-b120-195372900fd0.jpg)
# Zertan datza gure proeiktuak?
Arduino audio meter hau, gitarratik datorren seinalea irakurtzeko kapaza da. Sarreran txip amplifikagailu operazional baten bidez seinalea handitu eta arduinoak irakurri egiten du. Seinalea plasmatzeko, arduinoak inpultsu bidez LED matrizeetara bideratzen du seinalea, LED-ak piztuz eta hainbat forma, irudi sortuz.
![audio_meter_parts](https://user-images.githubusercontent.com/99732982/154352142-e0f3fdf2-2d65-49c8-85d6-b3fa0e2631d5.jpg)
# Funtzionamendua:
Jatorrizko audio-sarrera ez ukitzeko eta ez aldatzeko diseinatuta dago zirkuitua. ADC Arduinoak gitarraren seinalea irakurriko du LED pantailaren animazioa sortzeko, zaratarik eta aldaketarik gehitu gabe. Zirkuituak 3 bloke ditu: sarrera Etapa eta LED Matrizeak eta Elikadura Iturria:
![hardware-configuration](https://user-images.githubusercontent.com/99732982/154352680-564505e4-4d4d-4591-a9f2-4b1db76d646b.jpg)
- Sarrera analogikoko etapa: audio-sarrerako seinale ahula anplifikatu eta iragazten da, UNO ADC Arduinorako prestatuz (Konbertitzaile analogikotik digitalera). Errailetik errailerako anplifikadore operazionala (MCP6002) erabiltzen da seinalea anplifikatzeko (2-30 aldiz irabazi-potentziometroaren arabera), audio-sarrerako edozein seinale erabili ahal izateko.

- 8x8ko LED kontrolagailuak eta matrizeak: "Anodo arrunteko" lau matrize erabiltzen dira 16x16ko pantaila bat sortzeko. Lau MAX7219 txip erabiltzen dira matrizeak kontrolatzeko. Arduino UNO eta LED lineen arteko komunikazioa 3 DIN (Data IN), CLK (erlojua) eta Carga lineen bidez egiten da. LED Arduino liburutegi estandarra (LedControl.h) adibide gehienetan erabiltzen da.

- Elikadura-iturria: LED 8X8ren lau matrizeren erabilerak 4x8x8 = 256 LED egiten du guztira, eta, beraz, korrontea 500 mA-raino handitu daiteke (Vin = 9 a 12 V). Horregatik erabiltzen dugu VXO7805-1000 bat (1A gehienezko irteera-korrontea izateko gai dena). 7805 estandarrago bat ere erabil liteke, baina berotu egiten da.
![Arduino-Audio-Meter_Schematic_simple](https://user-images.githubusercontent.com/99732982/154353086-81763eea-389b-4e15-a146-7f4182ea565b.jpg)
# Nola programatu:

Proiektua ahalik eta errazena programatzeko, Arduinoko IDE estandarra erabiliko dugu. Efektu guztiak C formatuan programatuta daude. Tresna eta programa guztiak doakoak/kode irekikoak dira. 8x8ko LED matrizeak kontrolatzeko, LedControl liburutegia erabiltzen dugu.
