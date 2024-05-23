# plant
class Plant:
    def __init__(self, name, species, water_frequency, sunlight):
        self.name = name
        self.species = species
        self.water_frequency = water_frequency
        self.sunlight = sunlight

    def __str__(self):
        return f"{self.name} ({self.species}): Water every {self.water_frequency} days, requires {self.sunlight} sunlight"

class PlantManager:
    def __init__(self):
        self.plants = []

    def add_plant(self, name, species, water_frequency, sunlight):
        plant = Plant(name, species, water_frequency, sunlight)
        self.plants.append(plant)
        print(f"Added plant: {plant}")

    def list_plants(self):
        if not self.plants:
            print("No plants in the list.")
        else:
            for plant in self.plants:
                print(plant)

def main():
    manager = PlantManager()
    
    while True:
        print("\nPlant Manager")
        print("1. Add a new plant")
        print("2. List all plants")
        print("3. Exit")
        
        choice = input("Enter your choice: ")
        
        if choice == '1':
            name = input("Enter plant name: ")
            species = input("Enter plant species: ")
            water_frequency = input("Enter water frequency (in days): ")
            sunlight = input("Enter sunlight requirement (e.g., full sun, partial shade, shade): ")
            
            manager.add_plant(name, species, water_frequency, sunlight)
        
        elif choice == '2':
            manager.list_plants()
        
        elif choice == '3':
            print("Exiting the program.")
            break
        
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
