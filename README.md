# 🍫 Scho Ka Mesh

> ⚠️ **Aviso de Responsabilidad / Legal Disclaimer / Haftungsausschluss:**  
> **🇪🇸:** Queda bajo la responsabilidad exclusiva del usuario final garantizar que la fabricación, configuración y uso de estas placas o dispositivos cumpla con la legislación y normativa de telecomunicaciones aplicable en su país o región.  
> **🇬🇧:** It is the sole responsibility of the end user to ensure that the assembly, configuration, and operation of these PCBs comply with applicable local telecommunications laws and regulations.  
> **🇩🇪:** Es liegt in der alleinigen Verantwortung des Endbenutzers sicherzustellen, dass die Montage, Konfiguration und der Betrieb dieser Platinen den geltenden lokalen Telekommunikationsgesetzen und -vorschriften entsprechen.

---

## 🇪🇸 Castellano

### PCB circular para nodos Meshtastic compactos en latas Scho-Ka-Kola

**Scho Ka Mesh** es una placa circular diseñada específicamente para encajar a la perfección dentro de las icónicas latas metálicas de chocolate **Scho-Ka-Kola**. Permite crear un nodo Meshtastic portable, discreto y autónomo, aprovechando la profundidad de la lata para alojar una batería LiPo plana bajo la placa principal.

### 🛠️ Características Principales

#### 📻 Conectividad, Control y GPS
- **Compatibilidad Multi-Radio:** Soporta módulos **E22 / E22P**, **E80**, **E28** y **HT-RA62**.
- **Navegación / GPS:** Incluye huella dedicada para el módulo GPS **ATGM336H** de bajo consumo.
- **Cerebro (MCU):** NRF52840 Pro Micro / SuperMini de muy bajo consumo.
- **Sensor Integrado:** Espacio dedicado para un sensor ambiental **BME280** (presión, temperatura y humedad).

#### 🔋 Alimentación y Gestión
- **Formato Compacto:** Diseñada para colocarse sobre una **batería LiPo plana 1S** ajustada al fondo de la lata circular.
- **Regulación de Voltaje:** Compatible con módulos *boost* / *buck-boost* para garantizar la potencia óptima en transmisiones LoRa exigentes (E22 / E22P / E28).
- **Control Físico:** Incluye un interruptor de encendido/apagado general (ON/OFF) integrado en la placa.

> 💡 **Nota de Uso Importante:** Debido a que el chasis de la lata de Scho-Ka-Kola es metálico, actúa como una **jaula de Faraday** bloqueando las señales de radio. Es **imprescindible** utilizar un latiguillo *pigtail* U.FL/IPEX a SMA para sacar la antena LoRa (y del GPS si se requiere) al exterior mediante una perforación en la lata.

<details>
<summary><b>📦 Lista de Materiales (BOM) y Selección </b><i>(Haz clic para desplegar)</i></summary>
<br>

#### 🔹 1. Componentes Base (Comunes para todos los montajes)
| Componente | Descripción / Modelo | Cant. | Enlace de Compra | Notas |
| :--- | :--- | :---: | :--- | :--- |
| **MCU / Cerebro** | NRF52840 Pro Micro / SuperMini | 1 | [🛒 Comprar](https://es.aliexpress.com/item/1005007383375306.html) | Microcontrolador principal. |
| **Módulo GPS** | ATGM336H | 1 | [🛒 Comprar](https://es.aliexpress.com/item/1005009691244562.html) | Módulo GPS/GNSS de bajo consumo. |
| **Sensor (Opcional)** | Módulo BME280 | 1 | [🛒 Comprar](https://es.aliexpress.com/item/1005002963592665.html) | Medición de temp, humedad y presión. |
| **Batería** | Batería LiPo Plana 1S (3.7V) | 1 | [🛒 Comprar](https://es.aliexpress.com/) | Batería tipo *pouch* para el fondo de la lata. |
| **Protección Batería**| Circuito BMS 1S | 1 | [🛒 Comprar](https://es.aliexpress.com/item/1005008217119006.html) | Protección contra sobrecarga y sobredescarga. |
| **Interruptor** | Encendido/Apagado | 1 | [🛒 Comprar](https://es.aliexpress.com/item/1005006143122311.html) | Interruptor general. |
| **Resistencias 1206** | 1x 680K, 1x 1M (o 2x 1M) | 2 | [🛒 Comprar](https://es.aliexpress.com/item/1005002991902748.html) | Divisor de tensión para monitorear la batería. |
| **Botón Reset** | Pulsador táctil | 1 | [🛒 Comprar](https://es.aliexpress.com/item/4001125532910.html) | Pulsador SMD/PTH para reset. |

#### 🔹 2. Guía de Selección de Componentes Configurables
**1️⃣ Paso 1: Elige el Módulo de Radio (Selecciona 1)**
| Opción | Módulo | Descripción / Características | Enlace |
| :--- | :--- | :--- | :---: |
| **A** | **E22P** | Semtech SX1262/SX1268. Máximo alcance y potencia LoRa. (433/868/915 MHz) | [🛒 Comprar](https://es.aliexpress.com/item/1005010297548005.html) |
| **B** | **E22** | Semtech SX1262/SX1268. Sin filtros integrados, más bandas disponibles. | [🛒 Comprar](https://es.aliexpress.com/item/1005009741346732.html) |
| **C** | **E80** | LoRa de ultra bajo consumo para 433/868 MHz y 2.4GHz. | [🛒 Comprar](https://es.aliexpress.com/item/1005009119868850.html) |
| **D** | **E28** | LoRa a 2.4GHz. Ideal para alta velocidad o redes locales cortas. | [🛒 Comprar](https://es.aliexpress.com/item/1005010288386483.html) |
| **E** | **HT-RA62** | Módulo compacto basado en SX1262. | [🛒 Comprar](https://es.aliexpress.com/item/1005008363549136.html) |

**2️⃣ Paso 2: Elige la Regulación / Boost para la Radio (Solo E22 / E22P / E28)**
| Opción | Modo de Alimentación | Descripción / Recomendación | Enlace |
| :--- | :--- | :--- | :---: |
| **A (E28)** | **Modo QRP** | Sin regulador. La radio usa los 3.3V del Pro Micro (Baja potencia). | N/A |
| **B** | **Mini Buck-Boost** | Mini módulo para alimentar el E22/E28 a 5V/3.3V respectivamente. | [🛒 Comprar](https://es.aliexpress.com/item/1005011637436564.html) |
| **C (E22/P)** | **Boost 5V 3A** | Elevador de tensión para alimentar el E22/E22P a 5V. | [🛒 Comprar](https://es.aliexpress.com/item/1005008051438437.html) |
| **D (E22/P)** | **HW-085** | Opción mini para alimentar el E22/E22P a 5V. | [🛒 Comprar](https://es.aliexpress.com/item/1005007013856492.html) |
| **E** | **TPS63020** | Opción mini para alimentar el E22/E28 a 5V/3.3V respectivamente. | [🛒 Comprar](https://es.aliexpress.com/item/1005008099216597.html) |
</details>

---

## 🇬🇧 English

### Circular PCB for compact Meshtastic nodes in Scho-Ka-Kola tins

**Scho Ka Mesh** is a circular PCB tailored to fit precisely inside the iconic **Scho-Ka-Kola** chocolate tins. It turns a standard round tin into a portable, discrete, and self-contained Meshtastic node, utilizing the tin's depth to store a flat LiPo battery beneath the main board.

### 🛠️ Key Features

#### 📻 Connectivity, Control & GPS
- **Multi-Radio Compatibility:** Supports **E22 / E22P**, **E80**, **E28**, and **HT-RA62** modules.
- **GPS Navigation:** Integrated footprint for a low-power **ATGM336H** GPS module.
- **Brain / MCU:** Ultra-low-power NRF52840 Pro Micro / SuperMini.
- **Integrated Sensor:** Dedicated footprint for a **BME280** environmental sensor (pressure, temperature, and humidity).

#### 🔋 Power & Management
- **Compact Form Factor:** Designed to sit atop a **flat 1S LiPo battery (pouch cell)** nestled at the bottom of the circular tin.
- **Voltage Regulation:** Supports *boost* / *buck-boost* modules to reliably drive power-hungry LoRa modules (E22 / E22P / E28).
- **Physical Control:** Onboard master ON/OFF power toggle switch included.

> 💡 **Important Usage Note:** Because the body of the Scho-Ka-Kola tin is made of metal, it acts as a **Faraday cage**, blocking RF signals. It is **mandatory** to route the antennas to the outside using an IPEX/U.FL-to-SMA pigtail cable and mounting a bulkhead SMA connector through a hole drilled into the side or lid of the tin.

<details>
<summary><b>📦 Bill of Materials (BOM) & Selection Guide </b><i>(Click to expand)</i></summary>
<br>

#### 🔹 1. Base Components (Common for all builds)
| Component | Description / Model | Qty | Purchase Link | Notes |
| :--- | :--- | :---: | :--- | :--- |
| **MCU / Brain** | NRF52840 Pro Micro / SuperMini | 1 | [🛒 Buy](https://es.aliexpress.com/item/1005007383375306.html) | Low-power main microcontroller. |
| **GPS Module** | ATGM336H | 1 | [🛒 Buy](https://es.aliexpress.com/item/1005009691244562.html) | Low-power GPS/GNSS module. |
| **Sensor (Optional)** | BME280 Module | 1 | [🛒 Buy](https://es.aliexpress.com/item/1005002963592665.html) | Temp, humidity, and pressure. |
| **Battery** | Flat 1S LiPo Battery (3.7V) | 1 | [🛒 Buy](https://es.aliexpress.com/) | Flat pouch battery mounted beneath PCB. |
| **Battery Protection**| 1S BMS Circuit | 1 | [🛒 Buy](https://es.aliexpress.com/item/1005008217119006.html) | Overcharge/overdischarge protection. |
| **Switch** | Power ON/OFF Switch | 1 | [🛒 Buy](https://es.aliexpress.com/item/1005006143122311.html) | Main power toggle switch. |
| **1206 Resistors** | 1x 680K, 1x 1M (or 2x 1M) | 2 | [🛒 Buy](https://es.aliexpress.com/item/1005002991902748.html) | Resistors for battery voltage monitoring. |
| **Reset Button** | Tactile Push Button | 1 | [🛒 Buy](https://es.aliexpress.com/item/4001125532910.html) | SMD/PTH reset push button. |

#### 🔹 2. Configurable Component Selection Guide
**1️⃣ Step 1: Select the Radio Module (Select 1)**
| Option | Module | Description / Features | Purchase Link |
| :--- | :--- | :--- | :---: |
| **A** | **E22P** | Semtech SX1262/SX1268. Recommended for ultra-long-range links. (433/868/915 MHz) | [🛒 Buy](https://es.aliexpress.com/item/1005010297548005.html) |
| **B** | **E22** | Semtech SX1262/SX1268. Unfiltered variant, additional bands. | [🛒 Buy](https://es.aliexpress.com/item/1005009741346732.html) |
| **C** | **E80** | Ultra-low power LoRa module for 433/868 MHz and 2.4GHz. | [🛒 Buy](https://es.aliexpress.com/item/1005009119868850.html) |
| **D** | **E28** | 2.4GHz LoRa module. Ideal for high data throughput / local mesh. | [🛒 Buy](https://es.aliexpress.com/item/1005010288386483.html) |
| **E** | **HT-RA62** | Compact module based on SX1262. | [🛒 Buy](https://es.aliexpress.com/item/1005008363549136.html) |

**2️⃣ Step 2: Select Radio Regulation / Boost Module (Only for E22 / E22P / E28)**
| Option | Power Mode | Description | Purchase Link |
| :--- | :--- | :--- | :---: |
| **A (E28)** | **QRP Mode** | No dedicated regulator. The radio uses the Pro Micro 3.3V rail. | N/A |
| **B** | **Mini Buck-Boost**| Compact option to power E22/E28 at 5V/3.3V respectively. | [🛒 Buy](https://es.aliexpress.com/item/1005011637436564.html) |
| **C (E22/P)** | **Boost 5V 3A** | Power module to supply a stable 5V to the E22/E22P. | [🛒 Buy](https://es.aliexpress.com/item/1005008051438437.html) |
| **D (E22/P)** | **HW-085** | Mini boost option to power E22/E22P at 5V. | [🛒 Buy](https://es.aliexpress.com/item/1005007013856492.html) |
| **E** | **TPS63020** | Mini option to power E22/E28 at 5V/3.3V respectively. | [🛒 Buy](https://es.aliexpress.com/item/1005008099216597.html) |
</details>

---

## 🇩🇪 Deutsch

### Kreisförmige Leiterplatte (PCB) für kompakte Meshtastic-Knoten in Scho-Ka-Kola-Dosen

**Scho Ka Mesh** ist eine kreisförmige Platine, die speziell entwickelt wurde, um perfekt in die ikonischen Schokoladen-Blechdosen von **Scho-Ka-Kola** zu passen. Sie verwandelt eine Standarddose in einen tragbaren, diskreten und eigenständigen Meshtastic-Knoten, wobei die Tiefe der Dose genutzt wird, um einen flachen LiPo-Akku unter der Hauptplatine unterzubringen.

### 🛠️ Hauptmerkmale

#### 📻 Konnektivität, Steuerung & GPS
- **Multi-Radio-Kompatibilität:** Unterstützt **E22 / E22P**, **E80**, **E28** und **HT-RA62** Module.
- **GPS-Navigation:** Integrierter Fußabdruck für ein energiesparendes **ATGM336H** GPS-Modul.
- **Gehirn / MCU:** Extrem stromsparender NRF52840 Pro Micro / SuperMini.
- **Integrierter Sensor:** Spezieller Fußabdruck für einen **BME280** Umweltsensor (Luftdruck, Temperatur und Luftfeuchtigkeit).

#### 🔋 Stromversorgung & Management
- **Kompaktes Format:** Entwickelt, um über einem **flachen 1S-LiPo-Akku (Pouch-Zelle)** platziert zu werden, der auf dem Boden der runden Dose liegt.
- **Spannungsregelung:** Unterstützt *Boost-* / *Buck-Boost-* Module für eine zuverlässige Stromversorgung leistungsstarker LoRa-Module (E22 / E22P / E28).
- **Physische Steuerung:** Integrierter Haupt-Ein/Aus-Schalter (ON/OFF) auf der Platine.

> 💡 **Wichtiger Nutzungshinweis:** Da das Gehäuse der Scho-Ka-Kola-Dose aus Metall besteht, wirkt es als **Faradayscher Käfig** und blockiert HF-Signale. Es ist **zwingend erforderlich**, die Antennen mit einem IPEX/U.FL-auf-SMA-Pigtail-Kabel nach außen zu führen und einen SMA-Steckverbinder durch ein in die Seite oder den Deckel der Dose gebohrtes Loch zu montieren.

<details>
<summary><b>📦 Stückliste (BOM) & Auswahlleitfaden </b><i>(Zum Ausklappen klicken)</i></summary>
<br>

#### 🔹 1. Basiskomponenten (Für alle Konfigurationen erforderlich)
| Komponente | Beschreibung / Modell | Menge | Kauflink | Hinweise |
| :--- | :--- | :---: | :--- | :--- |
| **MCU / Gehirn** | NRF52840 Pro Micro / SuperMini | 1 | [🛒 Kaufen](https://es.aliexpress.com/item/1005007383375306.html) | Energiesparender Haupt-Mikrocontroller. |
| **GPS-Modul** | ATGM336H | 1 | [🛒 Kaufen](https://es.aliexpress.com/item/1005009691244562.html) | Energiesparendes GPS/GNSS-Modul. |
| **Sensor (Optional)** | BME280 Modul | 1 | [🛒 Kaufen](https://es.aliexpress.com/item/1005002963592665.html) | Temperatur, Feuchtigkeit und Druck. |
| **Akku** | Flacher 1S LiPo-Akku (3,7V) | 1 | [🛒 Kaufen](https://es.aliexpress.com/) | Flacher Akku für den Boden der Dose. |
| **Akku-Schutz** | 1S BMS-Schaltung | 1 | [🛒 Kaufen](https://es.aliexpress.com/item/1005008217119006.html) | Überlade-/Tiefentladeschutz. |
| **Schalter** | Ein/Aus-Schalter | 1 | [🛒 Kaufen](https://es.aliexpress.com/item/1005006143122311.html) | Hauptschalter (ON/OFF). |
| **1206 Widerstände** | 1x 680K, 1x 1M (oder 2x 1M) | 2 | [🛒 Kaufen](https://es.aliexpress.com/item/1005002991902748.html) | Spannungsteiler zur Akkuüberwachung. |
| **Reset-Taster** | Taktiler Druckschalter | 1 | [🛒 Kaufen](https://es.aliexpress.com/item/4001125532910.html) | SMD/PTH-Taster für Reset. |

#### 🔹 2. Leitfaden zur Auswahl konfigurierbarer Komponenten
**1️⃣ Schritt 1: Wählen Sie das Funkmodul (1 auswählen)**
| Option | Modul | Beschreibung / Funktionen | Kauflink |
| :--- | :--- | :--- | :---: |
| **A** | **E22P** | Semtech SX1262/SX1268. Empfohlen für maximale LoRa-Reichweite. (433/868/915 MHz) | [🛒 Kaufen](https://es.aliexpress.com/item/1005010297548005.html) |
| **B** | **E22** | Semtech SX1262/SX1268. Ohne Filter, zusätzliche Frequenzbänder. | [🛒 Kaufen](https://es.aliexpress.com/item/1005009741346732.html) |
| **C** | **E80** | LoRa-Modul mit extrem niedrigem Stromverbrauch für 433/868 MHz und 2,4 GHz. | [🛒 Kaufen](https://es.aliexpress.com/item/1005009119868850.html) |
| **D** | **E28** | 2,4 GHz LoRa-Modul. Ideal für hohen Datendurchsatz / lokale Mesh-Netzwerke. | [🛒 Kaufen](https://es.aliexpress.com/item/1005010288386483.html) |
| **E** | **HT-RA62** | Kompaktes Modul basierend auf dem SX1262. | [🛒 Kaufen](https://es.aliexpress.com/item/1005008363549136.html) |

**2️⃣ Schritt 2: Wählen Sie das Spannungsregelungsmodul (Nur für E22 / E22P / E28)**
| Option | Energiemodus | Beschreibung | Kauflink |
| :--- | :--- | :--- | :---: |
| **A (E28)** | **QRP-Modus** | Kein eigener Regler. Das Funkgerät nutzt die 3,3-V-Schiene des Pro Micro. | N/A |
| **B** | **Mini Buck-Boost**| Kompakte Option zur Versorgung des E22/E28 mit 5V bzw. 3,3V. | [🛒 Kaufen](https://es.aliexpress.com/item/1005011637436564.html) |
| **C (E22/P)** | **Boost 5V 3A** | Leistungsmodul zur Versorgung des E22/E22P mit stabilen 5V. | [🛒 Kaufen](https://es.aliexpress.com/item/1005008051438437.html) |
| **D (E22/P)** | **HW-085** | Mini-Boost-Option für E22/E22P mit 5V. | [🛒 Kaufen](https://es.aliexpress.com/item/1005007013856492.html) |
| **E** | **TPS63020** | Mini-Option zur Versorgung des E22/E28 mit 5V bzw. 3,3V. | [🛒 Kaufen](https://es.aliexpress.com/item/1005008099216597.html) |
</details>

---

## 📋 Historial de Cambios / Changelog

<details>
<summary><b>Click to expand / Clic para desplegar / Zum Ausklappen klicken</b></summary>
<br>

### 🟢 v1.0 - Initial (Untested)
- **Diseño / Design:** Versión inicial de la PCB circular adaptada para latas de Scho-Ka-Kola / Initial circular PCB design customized for Scho-Ka-Kola tins.
- **GPS:** Integración de huella dedicada para módulo GPS ATGM336H / Dedicated footprint for ATGM336H GPS module.
- **Radio:** Soporte multi-módulo (E22/E22P, E80, E28, HT-RA62) / Multi-module support (E22/E22P, E80, E28, HT-RA62).
- **Alimentación / Power:** Rieles para reguladores / boosters dedicados para el E22/E22P/E28 y soporte de batería LiPo plana con BMS / Dedicated booster rails for E22/E22P/E28 and support for flat LiPo battery with BMS.
- **Sensores / Sensors:** Huella integrada para sensor BME280 / Integrated footprint for BME280 sensor.
</details>

---

## 📐 Vista del Diseño / Design View

A continuación se muestra el render 3D de la PCB / Below is the 3D PCB render / Unten sehen Sie das 3D-Renderbild der PCB:

<p align="center">
  <img width="600" alt="Scho Ka Mesh Render" src="https://github.com/user-attachments/assets/fae52758-a531-4e2f-b15c-4c7a1d588d80" />
</p>
