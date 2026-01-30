# 3D-Print-filament-Maker
Mechanics and electronics for a fully functual filament melter, wich isn`t exspensive.(granulate melting)


Links for the Parts:
https://www.feinewerkzeuge.de/Schlangenbohrer-13-mm-Gesamtlaenge-190-mm/312307
https://www.amazon.de/-/en/AWJUWHBJ/dp/B0FXBT1N8M?tag=operagx-def-sp-co2-de-21
https://www.obi.de/p/4476206/arcansas-rundrohr-1-6-cm-x-100-cm-stahl?wt_mc=ogs.local...&storeId=131
https://www.amazon.de/AZDelivery-Kraftempfindlich-Drucksensor-Druckerkennung-Kraftsensor/dp/B0BV7B64C5/262-0193756-6053508?pd_rd_w=AVsZJ&content-id=amzn1.sym.716712ef-df33-47df-ae89-8f57d61f71e1&pf_rd_p=716712ef-df33-47df-ae89-8f57d61f71e1&pf_rd_r=FT4S45J42JPN1NJ4SH52&pd_rd_wg=7uoqY&pd_rd_r=d721b43b-5614-4be4-b142-a5ef7faf3a43&pd_rd_i=B0BV7B64C5&th=1&tag=operagx-def-sp-co2-de-21
electrical components:
 L7805CV //Voltage regulator
 IRFP460PBF //N-Channel MosFet
 TLC/1A-101M-00 TLC/1A-101M-00 //ring Inductor
 MKP 10 6800pF 10% 400V RM7,5 //MKP capacitor
 MEAN WELL IRM-02-12 AC/DC //low power supply(alternative for LM 7805)
 B78108S1475J000 B78108S1475J000 // Inductor
 B57164K103J B57164K103J //Thermistor
 BZX85C15-TAP //Zener Diode
 various Resistors
 various capacitors 
 Heat sink for transistors
 
 

The Mashine will use Induktion heating, wich is cheap an simple more information you can get here:
https://www.uihm.com/de/Induction-Heating-Technology/Base-details-of-High-Frequency-Induction-Heating.html
for the circuit i will use a fullbridge oscillator(PWM controlled) and a dc 12V source 
also you can build the power supply yourself(Circuit_1.jrps) or just buy one with around 300W 12V
for the esp32 a LM 7805 IC is used

there are to diffrent methods available, with thickness sensor or without it.
