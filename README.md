# volvoclass Car:
    def __init__(self, brand, model, year, max_speed):
        self.brand = brand
        self.model = model
        self.year = year
        self.max_speed = max_speed
        self.current_speed = 0

    def accelerate(self, increase_speed):
        if self.current_speed + increase_speed > self.max_speed:
            self.current_speed = self.max_speed
        else:
            self.current_speed += increase_speed
        print(f"Accelerating... Current speed: {self.current_speed} km/h")

    def brake(self, decrease_speed):
        if self.current_speed - decrease_speed < 0:
            self.current_speed = 0
        else:
            self.current_speed -= decrease_speed
        print(f"Braking... Current speed: {self.current_speed} km/h")

    def car_status(self):
        print(f"Car: {self.brand} {self.model} ({self.year})")
        print(f"Max Speed: {self.max_speed} km/h")
        print(f"Current Speed: {self.current_speed} km/h")


# Create a Volvo car object
volvo_car = Car(brand="Volvo", model="XC90", year=2023, max_speed=240)

# Display the car's status
volvo_car.car_status()

# Simulate driving the car
volvo_car.accelerate(50)  # Accelerate to 50 km/h
volvo_car.accelerate(100)  # Accelerate by 100 km/h
volvo_car.brake(30)  # Brake by 30 km/h
volvo_car.brake(200)  # Brake to a full stop

# Display the final car's status
volvo_car.car_status()
