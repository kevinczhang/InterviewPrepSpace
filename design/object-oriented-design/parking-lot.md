---
description: Design a parking lot using object-oriented principles.
---

# Parking Lot

The wording of this question is vague, just as it would be in an actual interview. This requires you to have a conversation with your interviewer about what types of vehicles it can support, whether the parking lot has multiple levels, and so on. 

For our purposes right now, we'll make the following assumptions. We made these specific assumptions to add a bit of complexity to the problem without adding too much. If you made different assumptions, that's totally fine.

* The parking lot has multiple levels. Each level has multiple rows of spots.
* The parking lot can park motorcycles, cars, and buses.
* The parking lot has motorcycle spots, compact spots, and large spots.
* A motorcycle can park in any spot.
* A car can park in either a single compact spot or a single large spot.
* A bus can park in five large spots that are consecutive and within the same row. it cannot park in small spots.

In the below implementation, we have created an abstract class Vehicle, from which Car, Bus, and Motorcycle inherit. To handle the different parking spot sizes, we have just one class Parking Spot which has a member variable indicating the size.

```java
public enum VehicleSize { Motorcycle, Compact, Large }

public abstract class Vehicle {
    protected ArrayList<ParkingSpot> parkingSpots = new ArrayList<ParkingSpot>();
    protected String licensePlate;
    protected int spotsNeeded;
    protected VehicleSize size;

    public int getSpotsNeeded() { return spotsNeeded; }
    public VehicleSize getSize{} { return size; }

    /* Park vehicle in this spot (among others, potentially) */
    public void parkInSpot(ParkingSpot s) { parkingSpots.add(s); )

    /* Remove car from spot, and notify spot that it's gone */
    public void clearSpotsQ { ... }

    /* Checks if the spot is big enough for the vehicle (and is available). This
    * compares the SIZE only. It does not check if it has enough spots. */
    public abstract boolean canFitInSpot(ParkingSpot spot);
}

public class Bus extends Vehicle {
    public Bus() {
        spotsNeeded = 5;
        size = VehicleSize.Large;
    }

    /* Checks if the spot is a Large. Doesn't check num of spots */
    public boolean canFitInSpot(ParkingSpot spot) { ... }
}

public class Car extends Vehicle {
    public Car() {
        spotsNeeded = 1;
        size = VehicleSize.Compact;
    }

    /* Checks if the spot is a Compact or a Large. */
    public boolean canFitInSpot(ParkingSpot spot) { ... }
}

public class Motorcycle extends Vehicle {
    public Motorcycle() {
        spotsNeeded = 1;
        size = VehicleSize.Motorcycle;
    }

    public boolean canFitInSpot(ParkingSpot spot) { ... }
}
```



