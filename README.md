# Taller-Formativo

Overview

This project is a vehicle management system that incorporates both the Builder and Singleton design patterns to manage and create vehicle instances effectively. The system is designed to be flexible, maintainable, and scalable, catering to requirements for unique vehicle instances and complex object construction.

Features

Singleton Pattern:

Ensures that specific vehicle models (e.g., Ford Escape) have a single shared instance throughout the application.

Guarantees consistency and prevents duplicate instances.

Builder Pattern:

Facilitates step-by-step construction of complex vehicle objects.

Enables easy configuration and extension for additional vehicle attributes.

Project Structure

project/
├── src/
│   ├── singleton_vehicle.py       # Implementation of the Singleton pattern for unique vehicles
│   ├── vehicle_builder.py        # Implementation of the Builder pattern for flexible vehicle construction
│   ├── home_page.py              # Main client class integrating both patterns
│   └── vehicle.py                # Vehicle class representing the final product
├── tests/
│   ├── test_singleton.py         # Unit tests for Singleton implementation
│   ├── test_builder.py           # Unit tests for Builder implementation
│   └── test_integration.py       # Integration tests for combined functionality
├── README.md                     # Project documentation
└── requirements.txt              # Dependencies

Design Patterns Used

Singleton Pattern

Purpose: Ensure a single shared instance of a specific vehicle model.

Implementation:

SingletonVehicle class uses a private static attribute _instance to store the single instance.

Clients use the set_vehicle method to configure and retrieve the instance.

Builder Pattern

Purpose: Construct complex Vehicle objects step-by-step, allowing customization and easy extension.

Implementation:

VehicleBuilder provides methods like set_model, set_color, and set_property to configure the vehicle.

The build method returns a fully constructed Vehicle instance.

How to Run the Project

Clone the Repository:

git clone https://github.com/yourusername/vehicle-management-system.git
cd vehicle-management-system

Install Dependencies:

pip install -r requirements.txt

Run the Application:

python src/home_page.py

Run Tests:

pytest tests/

Example Usage

Singleton Example

from singleton_vehicle import SingletonVehicle

# Create a unique instance of Ford Escape
singleton = SingletonVehicle()
escape = singleton.set_vehicle(model="Escape", color="Red", brand="Ford")
print(escape)  # Output: {'model': 'Escape', 'color': 'Red', 'brand': 'Ford'}

Builder Example

from vehicle_builder import VehicleBuilder

# Construct a vehicle using the Builder
builder = VehicleBuilder()
vehicle = (builder.set_model("Mustang")
                .set_color("Blue")
                .set_brand("Ford")
                .set_year(2025)
                .set_property("horsepower", 450)
                .build())
print(vehicle)  # Output: {'model': 'Mustang', 'color': 'Blue', 'brand': 'Ford', ...}

Future Enhancements

Extend the Builder pattern to support additional vehicle types (e.g., electric, hybrid).

Incorporate a Factory Method for dynamic vehicle model creation.

Add a database integration to persist vehicle data.

Contributing

Fork the repository.

Create a new branch for your feature (git checkout -b feature-name).

Commit your changes (git commit -m 'Add new feature').

Push to the branch (git push origin feature-name).

Open a Pull Request.
