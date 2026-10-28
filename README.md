### Overview
The **WaterLevel** app connects to your local smart home setup via MQTT to display current liquid levels—such as rainwater cisterns, water tanks, or pools—through a live-rendered, organic water animation with rising bubbles across the entire LED matrix.


### Key Features
* **Dynamic Liquid Animation:** Real-time water level visualization (0–100%) with animated rising air bubbles.
* **Silky Smooth Subpixel Bubbles:** Continuous vertical subpixel anti-aliasing and gentle horizontal sine-wobble for fluid, realistic bubble motion.
* **Consistent Bubble Frequency:** Fixed virtual cycle height ensures bubble frequency and spawn rate stay perfectly steady and calm, even at low water levels.
* **Auto-Hide at 100%:** Optional setting to automatically skip and hide the app from the AWTRIX carousel rotation when the tank is full.
* **Live MQTT Integration:** Subscribes to any custom MQTT topic, automatically handling both raw numbers and JSON payloads (e.g., `{"percent": 75}` or `{"level": 75}`).
* **Clean No-Data State:** When waiting for initial sensor data, the display gently rests at a low baseline and shows `--%` in amber instead of misleading values.
* **Adaptive Text Shadow:** Subtle ambient drop-shadow effect rendered behind text and numbers to ensure maximum contrast and legibility against water and bubbles.
* **Display Modes:**
  * **52×16 Variant:** Supports both high-visibility 10-pixel large bitmap font and standard font with free positioning (`left`, `center`, `right` / `top`, `middle`, `bottom`).
  * **32×8 Variant:** Clean, compact standard font permanently centered horizontally and vertically for optimal readability on the 8-pixel matrix.
* **Native Web UI Configuration:** Fully configurable via the AWTRIX-NG App settings menu.

### Configuration Options

#### 52×16 Variant
| Setting | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| **MQTT Topic** | Text | *(empty)* | MQTT topic publishing the level data. |
| **Wave & Bubble Speed** | Number (1–10) | `3` | Adjusts wave oscillation and bubble rise speed. |
| **Large Centered Text (ignores alignment)** | Select (`no` / `yes`) | `no` | Displays large 10px numbers centered on screen. When enabled, alignment options are bypassed. |
| **Text Shadow** | Select (`no` / `yes`) | `yes` | Soft drop-shadow behind text to enhance contrast and readability over moving waves. |
| **Hide when Full (100%)** | Select (`no` / `yes`) | `no` | Automatically hides the app from the rotation when the water level reaches 100%. |
| **Horizontal Alignment** | Select | `left` | Small text alignment: `left`, `center`, or `right`. |
| **Vertical Alignment** | Select | `top` | Small text alignment: `top`, `middle`, or `bottom`. |

#### 32×8 Variant
| Setting | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| **MQTT Topic** | Text | *(empty)* | MQTT topic publishing the level data. |
| **Bubble Speed** | Number (1–10) | `3` | Adjusts the rise speed of the air bubbles. |
| **Text Shadow** | Select (`no` / `yes`) | `yes` | Soft drop-shadow behind text to enhance contrast over the water. |
| **Hide when Full (100%)** | Select (`no` / `yes`) | `no` | Automatically hides the app from the rotation when the water level reaches 100%. |
