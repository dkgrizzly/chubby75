Colorlight 5A-75B V1.0 Hardware
===============================


Components
----------

* Lattice ECP5 `LFE5U-25F-6BG256C` ([product page](https://www.latticesemi.com/Products/FPGAandCPLD/ECP5))
* Winbond `25Q32JVSIQ`, 32 Mbits SPI flash ([datasheet](datasheets/w25q32jv_spi_revc_08302016.pdf))
* 2x Broadcom `B50612D` Gigabit Ethernet PHYs ([datasheet](datasheets/B50610-DS07-RDS.pdf))
* 2x ESMT `M12L16161A-5T` 1M x 16bit 200MHz SDRAMs (organized as 1M x 32bit) ([datasheet](datasheets/M12L16161A.pdf))
* 12x `74HC245T` Octal Bidirectional Transceiver (used for level translation to 5V)


PCB overview
------------

![PCB front](images/cl-5a-75b-v70-front.jpg)
![PCB back](images/cl-5a-75b-v70-back.jpg)


Definitions
-----------


Power
-----


JTAG
----

JTAG is available on a 4-pin header next to the FPGA (U33). VCC/GND are available on a 2-pin header nearby.

| Pin | Function |
|-----|----------|
| J27 | TCK      |
| J31 | TMS      |
| J32 | TDI      |
| J30 | TDO      |
|     |          |
| J33 | *3.3V*   |
| J34 | *GND*    |


SPI Flash
---------


Connections
===========

Clock
-----

A 25MHz clock is available at FPGA pin P6, and is also connected to both PHYs.

SDRAM, U29
----------

| U29 Pin | FPGA Pin |
|---------|----------|
| DQ0     | B13      |
| DQ1     | C11      |
| DQ2     | C10      |
| DQ3     | A11      |
| DQ4     | C9       |
| DQ5     | E8       |
| DQ6     | B6       |
| DQ7     | B9       |
| DQ8     | A6       |
| DQ9     | B5       |
| DQ10    | A5       |
| DQ11    | B4       |
| DQ12    | B3       |
| DQ13    | C3       |
| DQ14    | A2       |
| DQ15    | B2       |
| A0      | A9       |
| A1      | E10      |
| A2      | B12      |
| A3      | D13      |
| A4      | C12      |
| A5      | D11      |
| A6      | D10      |
| A7      | E9       |
| A8      | D9       |
| A9      | B7       |
| A10/AP  | C8       |
| BA      | A7       |
| LDQM    | *GND*    |
| UDQM    | *GND*    |
| CLK     | C6       |
| CKE     | *3.3V*   |
| ~CS     | *GND*    |
| ~RAS    | D7       |
| ~CAS    | E7       |
| ~WE     | C7       |

SDRAM, U32
----------

| U32 Pin | FPGA Pin |
|---------|----------|
| DQ0     | E2       |
| DQ1     | D3       |
| DQ2     | A4       |
| DQ3     | E4       |
| DQ4     | D4       |
| DQ5     | C4       |
| DQ6     | E5       |
| DQ7     | D5       |
| DQ8     | E6       |
| DQ9     | D6       |
| DQ10    | D8       |
| DQ11    | A8       |
| DQ12    | B8       |
| DQ13    | B10      |
| DQ14    | B11      |
| DQ15    | E11      |
| A0      | A9       |
| A1      | E10      |
| A2      | B12      |
| A3      | D13      |
| A4      | C12      |
| A5      | D11      |
| A6      | D10      |
| A7      | E9       |
| A8      | D9       |
| A9      | B7       |
| A10/AP  | C8       |
| BA      | A7       |
| LDQM    | *GND*    |
| UDQM    | *GND*    |
| CLK     | C6       |
| CKE     | *3.3V    |
| ~CS     | *GND*    |
| ~RAS    | D7       |
| ~CAS    | E7       |
| ~WE     | C7       |

PHY0, U3
----------

| U3 Pin  | FPGA Pin |
|---------|----------|
| GTXCLK  | M2       |
| TXD[0]  | L1       |
| TXD[1]  | L3       |
| TXD[2]  | P2       |
| TXD[3]  | L4       |
| TX\_EN  | M3       |
| RXC     | M1       |
| RXD[0]  | N1       |
| RXD[1]  | M5       |
| RXD[2]  | N5       |
| RXD[3]  | M6       |
| RXD\_DV | N6       |
| MDC     | P3       |
| MDIO    | T2       |
| ~RESET  | P5       |

PHY1, U7
----------

| U7 Pin  | FPGA Pin |
|---------|----------|
| GTXCLK  | M12      |
| TXD[0]  | T14      |
| TXD[1]  | R12      |
| TXD[2]  | R13      |
| TXD[3]  | R14      |
| TX\_EN  | R15      |
| RXC     | M16      |
| RXD[0]  | P13      |
| RXD[1]  | N13      |
| RXD[2]  | P14      |
| RXD[3]  | M15      |
| RXD\_DV | L15      |
| MDC     | P3       |
| MDIO    | T2       |
| ~RESET  | P5       |

Buffers
-------


LED, Button
-----------

There is a general purpose, FPGA controlled LED (DATA_LED-) at P11, active low (FPGA pin should be set to open drain).

Additionally, there is a button (J28, KEY+). When M13 is an input, pressing the button will read low, otherwise it will read high.

Connector J1
--------------

| J1 Pin| HUB75 pin | FPGA Pin | Buffer                         | Notes               |
|-------|-----------|----------|--------------------------------|---------------------|
| 1     | R0        |  F3      |                                |                     |
| 2     | G0        |  F1      |                                |                     |
| 3     | B0        |  G3      |                                |                     |
| 4     | *GND*     |  *GND*   |                                |                     |
| 5     | R1        |  G2      |                                |                     |
| 6     | G1        |  H3      |                                |                     |
| 7     | B1        |  H5      |                                |                     |
| 8     | E         |  F15     |                                |                     |
| 9     | A         |  L2      |                                |                     |
| 10    | B         |  K1      |                                |                     |
| 11    | C         |  J5      |                                |                     |
| 12    | D         |  K2      |                                |                     |
| 13    | CLK       |  B16     |                                |                     |
| 14    | STB       |  J14     |                                |                     |
| 15    | OE        |  F12     |                                |                     |
| 16    | *GND*     |  *GND*   |                                |                     |


Connector J2
--------------

| J2 Pin| HUB75 pin | FPGA Pin | Buffer                         | Notes               |
|-------|-----------|----------|--------------------------------|---------------------|
| 1     | R0        |  J4      |                                |                     |
| 2     | G0        |  K3      |                                |                     |
| 3     | B0        |  G1      |                                |                     |
| 4     | *GND*     |  *GND*   |                                |                     |
| 5     | R1        |  K4      |                                |                     |
| 6     | G1        |  C2      |                                |                     |
| 7     | B1        |  E3      |                                |                     |
| 8     | E         |  F15     |                                |                     |
| 9     | A         |  L2      |                                |                     |
| 10    | B         |  K1      |                                |                     |
| 11    | C         |  J5      |                                |                     |
| 12    | D         |  K2      |                                |                     |
| 13    | CLK       |  B16     |                                |                     |
| 14    | STB       |  J14     |                                |                     |
| 15    | OE        |  F12     |                                |                     |
| 16    | *GND*     |  *GND*   |                                |                     |


Connector J3
--------------

| J3 Pin| HUB75 pin | FPGA Pin | Buffer                         | Notes               |
|-------|-----------|----------|--------------------------------|---------------------|
| 1     | R0        |  H4      |                                |                     |
| 2     | G0        |  K5      |                                |                     |
| 3     | B0        |  P1      |                                |                     |
| 4     | *GND*     |  *GND*   |                                |                     |
| 5     | R1        |  R1      |                                |                     |
| 6     | G1        |  L5      |                                |                     |
| 7     | B1        |  F2      |                                |                     |
| 8     | E         |  F15     |                                |                     |
| 9     | A         |  L2      |                                |                     |
| 10    | B         |  K1      |                                |                     |
| 11    | C         |  J5      |                                |                     |
| 12    | D         |  K2      |                                |                     |
| 13    | CLK       |  B16     |                                |                     |
| 14    | STB       |  J14     |                                |                     |
| 15    | OE        |  F12     |                                |                     |
| 16    | *GND*     |  *GND*   |                                |                     |


Connector J4
--------------

| J4 Pin| HUB75 pin | FPGA Pin | Buffer                         | Notes               |
|-------|-----------|----------|--------------------------------|---------------------|
| 1     | R0        |  P4      |                                |                     |
| 2     | G0        |  R2      |                                |                     |
| 3     | B0        |  M8      |                                |                     |
| 4     | *GND*     |  *GND*   |                                |                     |
| 5     | R1        |  M9      |                                |                     |
| 6     | G1        |  T6      |                                |                     |
| 7     | B1        |  R6      |                                |                     |
| 8     | E         |  F15     |                                |                     |
| 9     | A         |  L2      |                                |                     |
| 10    | B         |  K1      |                                |                     |
| 11    | C         |  J5      |                                |                     |
| 12    | D         |  K2      |                                |                     |
| 13    | CLK       |  B16     |                                |                     |
| 14    | STB       |  J14     |                                |                     |
| 15    | OE        |  F12     |                                |                     |
| 16    | *GND*     |  *GND*   |                                |                     |


Connector J5
--------------

| J5 Pin| HUB75 pin | FPGA Pin | Buffer                         | Notes               |
|-------|-----------|----------|--------------------------------|---------------------|
| 1     | R0        | M11      |                                |                     |
| 2     | G0        | N11      |                                |                     |
| 3     | B0        | P12      |                                |                     |
| 4     | *GND*     | *GND*    |                                |                     |
| 5     | R1        | K15      |                                |                     |
| 6     | G1        | N12      |                                |                     |
| 7     | B1        | L16      |                                |                     |
| 8     | E         | F15      |                                |                     |
| 9     | A         | L2       |                                |                     |
| 10    | B         | K1       |                                |                     |
| 11    | C         | J5       |                                |                     |
| 12    | D         | K2       |                                |                     |
| 13    | CLK       | B16      |                                |                     |
| 14    | STB       | J14      |                                |                     |
| 15    | OE        | F12      |                                |                     |
| 16    | *GND*     | *GND*    |                                |                     |


Connector J6
--------------

| J6 Pin| HUB75 pin | FPGA Pin | Buffer                         | Notes               |
|-------|-----------|----------|--------------------------------|---------------------|
| 1     | R0        | K16      |                                |                     |
| 2     | G0        | J15      |                                |                     |
| 3     | B0        | J16      |                                |                     |
| 4     | *GND*     | *GND*    |                                |                     |
| 5     | R1        | J12      |                                |                     |
| 6     | G1        | H15      |                                |                     |
| 7     | B1        | G16      |                                |                     |
| 8     | E         | F15      |                                |                     |
| 9     | A         | L2       |                                |                     |
| 10    | B         | K1       |                                |                     |
| 11    | C         | J5       |                                |                     |
| 12    | D         | K2       |                                |                     |
| 13    | CLK       | B16      |                                |                     |
| 14    | STB       | J14      |                                |                     |
| 15    | OE        | F12      |                                |                     |
| 16    | *GND*     | *GND*    |                                |                     |


Connector J7
--------------

| J7 Pin| HUB75 pin | FPGA Pin | Buffer                         | Notes               |
|-------|-----------|----------|--------------------------------|---------------------|
| 1     | R0        | H13      |                                |                     |
| 2     | G0        | J13      |                                |                     |
| 3     | B0        | H12      |                                |                     |
| 4     | *GND*     | *GND*    |                                |                     |
| 5     | R1        | G14      |                                |                     |
| 6     | G1        | H14      |                                |                     |
| 7     | B1        | G15      |                                |                     |
| 8     | E         | F15      |                                |                     |
| 9     | A         | L2       |                                |                     |
| 10    | B         | K1       |                                |                     |
| 11    | C         | J5       |                                |                     |
| 12    | D         | K2       |                                |                     |
| 13    | CLK       | B16      |                                |                     |
| 14    | STB       | J14      |                                |                     |
| 15    | OE        | F12      |                                |                     |
| 16    | *GND*     | *GND*    |                                |                     |


Connector J8
--------------

| J8 Pin| HUB75 pin | FPGA Pin | Buffer                         | Notes               |
|-------|-----------|----------|--------------------------------|---------------------|
| 1     | R0        | A15      |                                |                     |
| 2     | G0        | F16      |                                |                     |
| 3     | B0        | A14      |                                |                     |
| 4     | *GND*     | *GND*    |                                |                     |
| 5     | R1        | E13      |                                |                     |
| 6     | G1        | B14      |                                |                     |
| 7     | B1        | A13      |                                |                     |
| 8     | E         | F15      |                                |                     |
| 9     | A         | L2       |                                |                     |
| 10    | B         | K1       |                                |                     |
| 11    | C         | J5       |                                |                     |
| 12    | D         | K2       |                                |                     |
| 13    | CLK       | B16      |                                |                     |
| 14    | STB       | J14      |                                |                     |
| 15    | OE        | F12      |                                |                     |
| 16    | *GND*     | *GND*    |                                |                     |

