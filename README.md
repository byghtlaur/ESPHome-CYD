## ESP32 Touch Display: Server Rack & Home Assistant Dashboard
An advanced ESPHome and LVGL-based touch interface for the ESP32 (ILI9341). This project provides a multi-page dashboard to monitor Home Assistant host metrics, NAS health, and local rack environmentals (temperature/humidity), while providing direct PWM hardware control for rack cooling fans.

🚀 Features
Multi-Page LVGL Interface: Smooth navigation between Home, Home Assistant, SkyNAS, Rack Status, and Fan Control pages.

Auto-Cycle Mode: Includes a "Pause/Play" feature to automatically rotate through status pages every 10 seconds.

Dynamic Hardware Control:

PWM Fan Control: Adjust rack fan speeds via a touch slider or increment buttons (+/- 10%).

RPM Monitoring: Real-time feedback of fan speed via pulse counter.

Smart Backlight Management:

Automatic sleep timer (60s) to preserve display life.

Wake-on-touch functionality.

Home Assistant Integration: Pulls real-time CPU usage, Memory, Temperature, and Humidity data directly from your HA entities.

Visual Status Indicators:

Animated gauge arcs for metrics.

Dynamic Wi-Fi signal strength bar (RSSI) in the top bar.

Color-coded alerts (labels turn red when CPU/Memory usage exceeds 90%).

🛠 Hardware Requirements
Controller: ESP32 (designed for standard DevKit or "Cheap Yellow Display" boards).

Display: ILI9341 SPI (320x240 resolution).

Touch: XPT2046 resistive touch controller.

Peripherals:

PWM-capable 12V/5V Fans (connected via MOSFET/Transistor to GPIO27).

Tachometer (RPM) feedback connected to GPIO22.
