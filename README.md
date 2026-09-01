Car Pooling System ( Project 2 )

## Overview
A simple Java application that represents ride booking system. The system manages Cars, Routes, and Passengers, and calculates trip cost based on the passenger type (Subscriber or NonSubscriber).

## Classes

**Route** : Represents a fixed trip route.
- pickUpAddress, destAddress, tripPrice
- Getters/setters.

**Car** : Represents a car available for booking.
- car code, maxCapacity, route (which is a Route object)
- Getters/setters.

**Passenger** (abstract, parent class) : Base class for all passenger types.
- attributes: name, ID, reservedCar
- Abstract methods:
  - reserveCar(Car car): reserves the car and returns the computed trip cost.
  - displayInfo(): overridden by subclasses to print passenger + trip details.
- the object from CAR type is reserved (with ed), and the abstract method is reserveCar

**SubscriberPassenger extends Passenger**
- Gets a fixed 50% discount on the trip price.
- reserveCar() reduces the car's seat count by 1 and returns trip cost after discount.

**NonSubscriberPassenger extends Passenger**
- Has a discCopoun boolean flag.
- If discCopoun == true → gets a 10% discount.
- If discCopoun == false → pays the full trip price.

## Exception Handling
reserveCar() throws an exception when the target car's maxCapacity is 0.

## Main
Shows a menu that allows the user to choose the wanted process.
1. Reserve a car: enter your name, browse available trips, pick a trip number, answer whether you're a subscriber and (if not) whether you have a discount coupon. The passenger is created and added to the passengers list, and the booking summary is printed.
2. List all available cars: shows every car that still has free seats, with its code, route, and price.
3. List all passengers: shows every passenger booked so far along with their trip info and remaining seats on their car.
4. Exit: ends the program.

## Already Existing Data
- 4 routes and 5 cars are created up front (one car, camry, has maxCapacity = 0 to show the "no seats left" case).
- 3 passengers are added: 1 subscriber and 2 nonSubscribers (one with a coupon, one without).
