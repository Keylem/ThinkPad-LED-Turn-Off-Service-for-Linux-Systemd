# ThinkPad LED Turn Off Service for Linux (Systemd)
 This systemd service let's you to turn off LED's  provided by the thinkpad_acpi kernel driver
 To enable it on a custom kernel --> Gentoo Wiki TODO
 How to install
 - Copy the provided dervice files to /etc/systemd/system directory
 - Change the LED locations on the services according to your setup: (you can find them at /sys/class/leds/ with tpacpi::x folder
Example:
[Service]
Type=exec
ExecStart=sh -c "echo 0 | sudo tee /sys/class/leds/tpacpi::power/brightness "

You can also disable multiple LEDs at once with using multiple ExecStart entries
[Service]
Type=exec
ExecStart=sh -c "echo 0 | sudo tee /sys/class/leds/tpacpi::power/brightness "
ExecStart=sh -c "echo 0 | sudo tee /sys/class/leds/tpacpi::lid_logo_dot/brightness "
