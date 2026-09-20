# 🍫 Scho Ka Mesh

> ⚠️ **Aviso de responsabilidad / Legal Disclaimer:**  
> **🇪🇸:** Queda bajo la responsabilidad exclusiva del usuario final garantizar que la fabricación, configuración y uso de estas placas o dispositivos cumpla con la legislación y normativa de telecomunicaciones aplicable en su país o región.  
> **🇬🇧:** It is the sole responsibility of the end user to ensure that the assembly, configuration, and operation of these PCBs comply with applicable local telecommunications laws and regulations.

---

## 🇪🇸 Castellano

### PCB circular para nodos Meshtastic compactos en latas Scho-Ka-Kola

**Scho Ka Mesh** es una placa circular diseñada específicamente para encajar a la perfección dentro de las icónicas latas metálicas de chocolate **Scho-Ka-Kola**. Permite crear un nodo Meshtastic portable, discreto y autónomo, aprovechando la altura de la lata para alojar una batería LiPo plana bajo la placa principal.

---

### 🛠️ Características Principales

#### 📻 Conectividad, Control y GPS
* **Compatibilidad Multi-Radio:** Soporta módulos **E22/E22P**, **E80**, **E28** y **HT-RA62**.
* **Navegación / GPS:** Incluye huella dedicada para módulo GPS **ATGM336H**.
* **Cerebro:** NRF52840 Pro Micro de bajo consumo.
* **Sensor Integrado:** Espacio dedicado para un sensor ambiental **BME280** (presión, temperatura y humedad).

#### 🔋 Alimentación y Gestión
* **Formato Compacto:** Diseñada para colocarse sobre una **batería LiPo plana 1S** ajustada al fondo de la lata circular.
* **Regulación de Voltaje:** Compatible con módulos boost / buck-boost para garantizar potencia óptima en transmisiones LoRa (E22/E22P/E28).
* **Control Físico:** Incluye un interruptor de encendido/apagado general en placa.

---

<details>
<summary><b>📦 Lista de Materiales (BOM) (Haz clic para desplegar)</b></summary>

<br>

#### 🔹 1. Componentes Base (Comunes para todos los montajes)
Estos componentes son necesarios independientemente de la configuración elegida:

| Componente | Descripción / Modelo | Cantidad | Enlace de Compra | Notas |
| :--- | :--- | :---: | :---: | :--- |
| **MCU / Cerebro** | NRF52840 Pro Micro / SuperMini | 1 | [🛒 Comprar](https://es.aliexpress.com/item/1005007383375306.html) | Microcontrolador principal de bajo consumo |
| **Módulo GPS** | ATGM336H | 1 | [🛒 Comprar](https://es.aliexpress.com/item/1005009691244562.html) | Módulo GPS/GNSS de bajo consumo |
| **Sensor Ambiental (opcional)** | Módulo BME280 | 1 | [🛒 Comprar](https://es.aliexpress.com/item/1005002963592665.html) | Medición de temperatura, humedad y presión |
| **Batería** | Batería LiPo Plana 1S (3.7V) | 1 | [🛒 Comprar](https://es.aliexpress.com/) | Batería plana para alojar bajo la PCB |
| **Protección Batería** | Circuito BMS 1S | 1 | [🛒 Comprar](https://es.aliexpress.com/item/1005008217119006.html) | Módulo de protección contra sobrecarga/sobredescarga |
| **Interruptor** | Interruptor Encendido/Apagado | 1 | [🛒 Comprar](https://es.aliexpress.com/item/1005006143122311.html) | Interruptor general de encendido |
| **Resistencias 1206** | 1x 680K 1x 1M (o 2x 1M) | 2 | [🛒 Comprar](https://es.aliexpress.com/item/1005002991902748.html) | Resistencias para monitorear el nivel de la batería |
| **Botón reset** | Botón de reset | 1 | [🛒 Comprar](https://es.aliexpress.com/item/4001125532910.html) | Pulsador SMD/PTH para reset |

---

#### 🔹 2. Guía de Selección de Componentes Configurables

Sigue estos pasos para seleccionar los componentes según la configuración de tu nodo:

##### 1️⃣ Paso 1: Elige el Módulo de Radio *(Selecciona 1)*

| Opción | Módulo | Descripción / Características | Enlace de Compra |
| :--- | :--- | :--- | :---: |
| **Opción A** | **E22P** | Semtech SX1262 / SX1268. Recomendado para enlaces de muy largo alcance y máxima potencia LoRa. Disponible en 433, 868 y 915 MHz | [🛒 Comprar](https://es.aliexpress.com/item/1005010297548005.html) |
| **Opción B** | **E22** | Semtech SX1262 / SX1268. Sin filtros integrados, disponible en más bandas | [🛒 Comprar](https://es.aliexpress.com/item/1005009741346732.html) |
| **Opción C** | **E80** | Módulo LoRa de bajo consumo de 433/868 MHz y 2.4GHz | [🛒 Comprar](https://es.aliexpress.com/item/1005009119868850.html) |
| **Opción D** | **E28** | Módulo LoRa de 2.4GHz. Ideal para alta velocidad de transmisión o redes locales. | [🛒 Comprar](https://es.aliexpress.com/item/1005010288386483.html) |
| **Opción E** | **HT-RA62** | Módulo compacto basado en SX1262. | [🛒 Comprar](https://es.aliexpress.com/item/1005008363549136.html) |

##### 2️⃣ Paso 2: Elige la Regulación / Boost para la Radio *(Solo para E22/E22P y E28)*

| Opción | Modo de Alimentación | Descripción / Recomendación | Enlace de Compra |
| :--- | :--- | :--- | :---: |
| **Opción A (E28)** | **Modo QRP** *(Sin regulador dedicado)* | La radio se alimenta directamente de los 3.3V del Pro Micro. Para transmisiones QRP con E28. | N/A |
| **Opción B** | **Mini Buck-Boost 3.3V / 5V** | Opción mini para alimentar el E22/E28 a 5V/3.3V respectivamente | [🛒 Comprar](https://es.aliexpress.com/item/1005011637436564.html) |
| **Opción C (E22/E22P)** | **Boost 5V 3A** | Opción para alimentar el E22/E22P a 5V | [🛒 Comprar](https://es.aliexpress.com/item/1005008051438437.html) |
| **Opción D (E22/E22P)** | **HW-085** | Opción mini para alimentar el E22/E22P a 5V | [🛒 Comprar](https://es.aliexpress.com/item/1005007013856492.html) |
| **Opción E** | **TPS63020** | Opción mini para alimentar el E22/E28 a 5V/3.3V respectivamente | [🛒 Comprar](https://es.aliexpress.com/item/1005008099216597.html) |

*(Enlaces no afiliados)*

</details>

---

> 💡 **Nota de uso:** Debido a que el chasis de la lata de Scho-Ka-Kola es metálico, actúa como jaula de Faraday. Es imprescindible utilizar un latiguillo pigtail U.FL/IPEX a SMA para sacar la antena LoRa (y del GPS si se requiere) al exterior mediante una perforación en la lata.

---

## 🇬🇧 English

### Circular PCB for compact Meshtastic nodes in Scho-Ka-Kola tins

**Scho Ka Mesh** is a circular PCB tailored to fit precisely inside iconic **Scho-Ka-Kola** chocolate tins. It turns a standard round tin into a portable, discrete, and self-contained Meshtastic node, utilizing the tin depth to store a flat LiPo battery beneath the main board.

---

### 🛠️ Key Features

#### 📻 Connectivity, Control & GPS
* **Multi-Radio Compatibility:** Supports **E22/E22P**, **E80**, **E28**, and **HT-RA62** modules.
* **GPS Navigation:** Integrated footprint for an **ATGM336H** GPS module.
* **Brain / MCU:** Low-power NRF52840 Pro Micro / SuperMini.
* **Integrated Sensor:** Dedicated footprint for a **BME280** environmental sensor (pressure, temperature, and humidity).

#### 🔋 Power & Management
* **Compact Form Factor:** Designed to sit atop a **flat 1S LiPo battery** nestled at the bottom of the circular tin.
* **Voltage Regulation:** Supports boost / buck-boost modules to reliably drive power-hungry LoRa modules (E22/E22P/E28).
* **Physical Control:** Onboard master ON/OFF power switch included.

---

<details>
<summary><b>📦 Bill of Materials (BOM) (Click to expand)</b></summary>

<br>

#### 🔹 1. Base Components (Common for all builds)
These components are required regardless of your chosen configuration:

| Component | Description / Model | Qty | Purchase Link | Notes |
| :--- | :--- | :---: | :---: | :--- |
| **MCU / Brain** | NRF52840 Pro Micro / SuperMini | 1 | [🛒 Buy](https://es.aliexpress.com/item/1005007383375306.html) | Low-power main microcontroller |
| **GPS Module** | ATGM336H | 1 | [🛒 Buy](https://es.aliexpress.com/item/1005001621844100.html) | Low-power GPS/GNSS module |
| **Environmental Sensor (optional)** | BME280 Module | 1 | [🛒 Buy](https://es.aliexpress.com/item/1005002963592665.html) | Temperature, humidity, and pressure sensing |
| **Battery** | Flat 1S LiPo Battery (3.7V) | 1 | [🛒 Buy](https://es.aliexpress.com/) | Flat pouch battery mounted beneath PCB |
| **Battery Protection** | 1S BMS Circuit | 1 | [🛒 Buy](https://es.aliexpress.com/item/1005008217119006.html) | Overcharge/overdischarge protection module |
| **Switch** | Power ON/OFF Switch | 1 | [🛒 Buy](https://es.aliexpress.com/item/1005006143122311.html) | Main power toggle switch |
| **1206 Resistors** | 1x 680K 1x 1M (or 2x 1M) | 2 | [🛒 Buy](https://es.aliexpress.com/item/1005002991902748.html) | Resistors for battery voltage monitoring |
| **Reset Button** | Reset Push Button | 1 | [🛒 Buy](https://es.aliexpress.com/item/4001125532910.html) | SMD/PTH reset push button |

---

#### 🔹 2. Configurable Component Selection Guide

Follow these steps to choose components based on your intended node setup:

##### 1️⃣ Step 1: Select the Radio Module *(Select 1)*

| Option | Module | Description / Features | Purchase Link |
| :--- | :--- | :--- | :---: |
| **Option A** | **E22P** | Semtech SX1262 / SX1268. Recommended for ultra-long-range links & maximum LoRa power. Available in 433, 868, and 915 MHz | [🛒 Buy](https://es.aliexpress.com/item/1005010297548005.html) |
| **Option B** | **E22** | Semtech SX1262 / SX1268. Unfiltered variant, available in additional frequency bands | [🛒 Buy](https://es.aliexpress.com/item/1005009741346732.html) |
| **Option C** | **E80** | Ultra-low power LoRa module for 433/868 MHz and 2.4GHz | [🛒 Buy](https://es.aliexpress.com/item/1005009119868850.html) |
| **Option D** | **E28** | 2.4GHz LoRa module. Ideal for high data throughput or local mesh networks. | [🛒 Buy](https://es.aliexpress.com/item/1005010288386483.html) |
| **Option E** | **HT-RA62** | Compact module based on SX1262. | [🛒 Buy](https://es.aliexpress.com/item/1005008363549136.html) |

##### 2️⃣ Step 2: Select Radio Regulation / Boost *(Only for E22/E22P and E28)*

| Option | Power Mode | Description / Recommendation | Purchase Link |
| :--- | :--- | :--- | :---: |
| **Option A (E28)** | **QRP Mode** *(No dedicated regulator)* | The radio is powered directly from the Pro Micro 3.3V rail. For QRP transmission with E28. | N/A |
| **Option B** | **Mini Buck-Boost 3.3V / 5V** | Compact option to power E22/E28 at 5V/3.3V respectively | [🛒 Buy](https://es.aliexpress.com/item/1005011637436564.html) |
| **Option C (E22/E22P)** | **Boost 5V 3A** | Power module to supply 5V to E22/E22P | [🛒 Buy](https://es.aliexpress.com/item/1005008051438437.html) |
| **Option D (E22/E22P)** | **HW-085** | Mini boost option to power E22/E22P at 5V | [🛒 Buy](https://es.aliexpress.com/item/1005007013856492.html) |
| **Option E** | **TPS63020** | Mini option to power E22/E28 at 5V/3.3V respectively | [🛒 Buy](https://es.aliexpress.com/item/1005008099216597.html) |

*(Non-affiliated links)*

</details>

---

> 💡 **Usage Note:** Since the metal body of the Scho-Ka-Kola tin acts as a Faraday cage, you must route antennas through an IPEX/U.FL-to-SMA pigtail and mount a bulkhead SMA connector through a hole drilled into the side or lid of the tin.

---

## 📋 Historial de Cambios / Changelog

<details>
<summary><b>Click to expand / Clic para desplegar</b></summary>

<br>

### 🟢 v1.0 - Initial, untested
* **Diseño / Design:** Versión inicial de la PCB circular adaptada para latas de Scho-Ka-Kola / Initial circular PCB design customized for Scho-Ka-Kola tins.
* **GPS:** Integración de huella dedicada para módulo GPS ATGM336H / Dedicated footprint for ATGM336H GPS module.
* **Radio:** Soporte multi-módulo (E22/E22P, E80, E28, HT-RA62) / Multi-module support (E22/E22P, E80, E28, HT-RA62).
* **Alimentación / Power:** Rieles para reguladores / boosters dedicados para el E22/E22P/E28 y soporte de batería LiPo plana con BMS / Dedicated booster rails for E22/E22P/E28 and support for flat LiPo battery with BMS.
* **Sensórica / Sensors:** Huella integrada para sensor BME280 / Integrated footprint for BME280 sensor.

</details>

---

## 📐 Vista del Diseño / Design View

A continuación se muestra el render 3D de la PCB / Below is the 3D PCB render:

<img width="697" height="682" alt="image" src="https://github.com/user-attachments/assets/fae52758-a531-4e2f-b15c-4c7a1d588d80" />
