from machine import Pin
import time

# Setup pins
led_pin = Pin(16, Pin.OUT)
button_pin = Pin(10, Pin.IN, Pin.PULL_DOWN)

# Initial states
led_on = 0
led_pin.value(led_on)
previous_button_state = 1
debounce_delay = 0.05

while True:
    current_button_state = button_pin.value()
    
    # Detect button press transition
    if current_button_state == 0 and previous_button_state == 1:
        time.sleep(debounce_delay)  # debounce delay
        if button_pin.value() == 0:  # confirm button still pressed
            led_on = 1 - led_on      # toggle LED state
            led_pin.value(led_on)
    
    previous_button_state = current_button_state
    time.sleep(0.01)
