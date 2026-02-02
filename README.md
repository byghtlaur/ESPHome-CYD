# 🖥️ ESP32 CYD Touch Dashboard
### ESP32-Powered Server Rack Monitor & Fan Controller

![ESPHome Version](https://img.shields.io/badge/ESPHome-2024.x-orange)
![License](https://img.shields.io/badge/License-MIT-blue)

**SkyNet** is a comprehensive monitoring solution for home server enthusiasts. Built using **ESPHome** and the **LVGL (Light and Versatile Graphics Library)**, it transforms a "Cheap Yellow Display" (CYD) into a tactical command center for your server rack.

---

## ✨ Key Features

* **Multi-Page UI**: Dedicated views for Home, Home Assistant host metrics, SkyNAS health, Rack Environmentals, and Fan Control.
* **Active Hardware Control**: 
    * **PWM Fan Management**: Adjust speeds via a touch-friendly slider or incremental $+/-$ buttons.
    * **Real-time RPM Feedback**: Monitor fan tachometer pulses directly on-screen.
* **Automation & Intelligence**:
    * **Auto-Cycle Mode**: Automatically rotates through status pages every 10 seconds.
    * **Smart Backlight**: Includes a 60-second sleep timer to prevent screen burn-in, with wake-on-touch support.
* **Dynamic Visuals**: 
    * Gauge arcs change color (blue to red) when CPU or Memory usage exceeds 90%.
    * Live 4-bar Wi-Fi RSSI signal indicator in the header.

---

## 🛠️ Hardware Requirements

* **Display**: ESP32 with ILI9341 (320x240) and XPT2046 resistive touch.
* **Sensors**: Integrated with Home Assistant entities for remote data.
* **Fan Control**: Supports 4-pin PWM fans (requires a logic level shifter or MOSFET for 12V fans).

| Component | Pin (GPIO) |
| :--- | :--- |
| **Backlight PWM** | 21 |
| **Fan PWM Output** | 27 |
| **Fan Tachometer (RPM)** | 22 |
| **TFT SPI (CLK/MOSI/MISO)** | 14 / 13 / 12 |
| **Touch SPI (CLK/MOSI/MISO)** | 25 / 32 / 39 |

---

## 🚀 Quick Start (Web Installer)

If you have enabled GitHub Pages for this repository, you can flash your device directly from your browser:

1.  Connect your ESP32 to your computer via USB.
2.  Visit the project's GitHub Pages URL.
3.  Click the **"Flash to Display"** button.
4.  Follow the prompts to connect and install the pre-compiled `firmware.bin`.

---

## 💻 Local Installation & Customization

If you want to modify the logic or use your own entities:

1.  **Clone the Repo**:
    ```bash
    git clone [https://github.com/byghtlaur/ESPHome-CYD.git](https://github.com/byghtlaur/ESPHome-CYD.git)
    ```
2.  **Configure Secrets**: Create a `secrets.yaml` in the root folder:
    ```yaml
    wifi_ssid: "Your_SSID"
    wifi_password: "Your_Password"
    api_encryption_key: "Your_Key"
    ota_password: "Your_Password"
    ```
3.  **Update Entities**: Edit `display.yaml` to match your Home Assistant sensor IDs.
4.  **Deploy**:
    ```bash
    esphome run display.yaml
    ```

---

## 📂 Project Structure

* `display.yaml`: The core ESPHome configuration and LVGL logic.
* `index.html`: Web-based flash installer for GitHub Pages.
* `manifest.json`: Metadata for the ESP-Web-Tools installer.
* `firmware.bin`: Pre-compiled binary for immediate deployment.

---

## 🤝 Contributing
Feel free to fork this project, submit PRs, or report issues. I'm always looking to add more pages (like UPS monitoring or Network throughput)!

---
*Created with ❤️ by byghtlaur*
