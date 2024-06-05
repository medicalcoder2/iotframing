# iotframing
Iot farming
import time

class SoilMoistureSensor:
    def __init__(self):
        self.moisture_level = 0
    
    def read_moisture_level(self):
        # Simulate reading from the sensor
        # In a real scenario, this would involve interacting with the sensor hardware
        # Here, we just generate a random value between 0 and 100
        import random
        self.moisture_level = random.randint(0, 100)
        return self.moisture_level

class WaterPump:
    def __init__(self):
        self.is_running = False
    
    def turn_on(self):
        # Simulate turning on the water pump
        # In a real scenario, this would involve activating a pump motor
        print("Water pump turned on")
        self.is_running = True
    
    def turn_off(self):
        # Simulate turning off the water pump
        # In a real scenario, this would involve deactivating a pump motor
        print("Water pump turned off")
        self.is_running = False

class FarmingSystem:
    def __init__(self):
        self.soil_sensor = SoilMoistureSensor()
        self.water_pump = WaterPump()
    
    def monitor_soil_moisture(self):
        moisture_level = self.soil_sensor.read_moisture_level()
        print("Soil moisture level:", moisture_level)
        return moisture_level
    
    def control_water_pump(self, moisture_level):
        if moisture_level < 30:
            self.water_pump.turn_on()
        else:
            self.water_pump.turn_off()

# Main function
if __name__ == "__main__":
    farming_system = FarmingSystem()
    
    # Continuously monitor soil moisture and control water pump
    while True:
        moisture_level = farming_system.monitor_soil_moisture()
        farming_system.control_water_pump(moisture_level)
        
        # Wait for some time before taking the next reading
        time.sleep(5)  # Adjust the time interval as needed
