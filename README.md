# 2.4Ghz Amazon RC Car Teardown
TOQIBO Electric Racing Car Off Road 1/16 Scale 2.4Ghz 50M 2WD High Speed Desert Buggy Vehicle Radio Controlled Monster Truck Rock Crawler Toy Car: [Amazon](https://www.amazon.com/gp/product/B071X95KBF)


# PCB
![PCB](car_pcb_annotated.png)



## Pads ##
- **F** Forward
- **R** Reverse
- **4.8V** Batt +, Unswitched 4.8v
- **R** Direction of steering motor - Right
- **L** Direction of steering motor - Left
- **VDD**  Batt +, Same as 4.8V, but switched
- **GND**  Batt -


## Components ##


### [FNK4421 Dual P-Channel Mosfet (Dark Blue)](FNK4421.pdf)

![FNK4421](FNK4421.png)

- P1 S2 -> **4.8V**
- P2 G2 -> 4.8V via 10K resistor
- P3 S1 -> **4.8V**
- P4 G1 -> 4.8V via 10K resistor
- P5,P6 D1 -> **R**
- P7,P8 D2 -> **F**



### [FNK9928 N-Channel Mosfet (Brown)](FNK9928.pdf)

![FNK9928](FNK9928.png)

- P1 S2 -> GND, MC P11 via resistor
- P2 G2 -> MC P11
- P3 S1 -> MC P0 via 10K resistor
- P4 G1 -> MC P10
- P5,P6 D1 -> **F**
- P7,P8 D2 -> **R**


### [MX612 Motor Driver (Pink)](http://pdf.datasheetbank.com/datasheet-download/ETC/191016.pdf)

![MX612](MX612.png)



- P1 (VCC) Vout of 622K vreg, MC P?
- P2 (INA) -> MC P9
- P3 (INB) -> MC P4
- P4 (VDD) -> **4.8V**
- P8 (OUTA) -> **R**
- P7, P6 (PGND,AGND) are ganged, and probably go to GND
- P5 (OUTB) -> **L**

### [2.4Ghz RX2 (Yellow)](2_4GRX2.pdf)


![2_4GRX2](2_4GRX2.png)


- P01 ANT
- P02 GND
- P03 VDD_IO
- P04 LT
- P05 VDD (connected to VDD IO)
- P06 TR -> ROM SCL  (flip function? this makes no sense)
- P07 SEL -> ROM SDA (Three cars with channel selection)
- P08 PRST
- P09 RT
- P10 BK 9928 Mosfet -> **F**
- P11 FR 9928 Mosfet -> **R**
- P12 GND
- P13 XTAL1 OSC
- P14 XTAL0 OSC
- P15 VDDL
- P16 ANTB




### 662K 3.3V Regulator (Light Blue)
![662K](662K.png)


- P1 GND from **VDD** via 4.7k resistor
- P2 Vout
- P3 Vin


### [ATMEL Two-Wire Serial EEProm AT24C02B (Red)](AT24C02B.pdf)

![AT24C02B](AT24C02B.png)

  - P1 (A0), P2 (A1), P3 (A2), P4 (GND) tied to GND
  - P8 VCC P5
  - P7 WP is unconnected
  - P6 (SCL) -> MC P6
  - P5 (SDA) -> MC P7





