# Project1
Perth Connect
#Name: Pramitha Dhanraj 
#Perth Connect app
#Python program to show app features

parking_spots = [
    {"id": 1, "location": "Perth CBD - Murray St", "available": True},
    {"id": 2, "location": "Elizabeth Quay", "available": False},
    {"id": 3, "location": "Kings Park", "available": True},
]
while True:
    print("\n=== Perth Connect Parking App ===")
    print("1. Show all parking spots")
    print("2. Book a parking spot")
    print("3. Release a parking spot")
    print("4. Exit")

    choice = input("Enter your choice (1-4): ")

    if choice == "1":
        print("\n--- Parking Spots ---")
        for spot in parking_spots:
            status = "Available ✅" if spot["available"] else "Booked ❌"
            print(
                f"ID: {spot['id']} | Location: {spot['location']} | Status: {status}")

    elif choice == "2":
        spot_id = int(input("Enter Spot ID to book: "))
        found = False
        for spot in parking_spots:
            if spot["id"] == spot_id:
                found = True
                if spot["available"]:
                    spot["available"] = False
                    print(f"Spot {spot_id} booked successfully ✅")
                else:
                    print(f"Spot {spot_id} is already booked ❌")
        if not found:
            print("Spot not found ❌")

    elif choice == "3":
        spot_id = int(input("Enter Spot ID to release: "))
        found = False
        for spot in parking_spots:
            if spot["id"] == spot_id:
                found = True
                if not spot["available"]:
                    spot["available"] = True
                    print(f"Spot {spot_id} released and now available ✅")
                else:
                    print(f"Spot {spot_id} is already available")
        if not found:
            print("Spot not found ❌")

    elif choice == "4":
        print("Thank you for using Perth Connect App 🚗")
        break

    else:
        print("Invalid choice, please try again ❌")
