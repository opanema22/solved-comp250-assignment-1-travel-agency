Download Link: https://assignmentchef.com/product/solved-comp250-assignment-1-travel-agency
<br>
For this assignment you will write several classes to simulate an online travel agency. Note that for this assignment to be feasible in two weeks, a lot of simplifications have been made. For instance, we are completely ignoring time throughout the assignment. Make sure to follow the instructions below very closely. Note that in addition to the required methods, you are free to add as many other <strong>private </strong>methods as you want (no other additional method is allowed). You are <strong>not </strong>allowed to add any additional fields (whether they would be private or public) unless it is stated otherwise. Finally, whenever you are required to compare two strings you can ignore case of the characters.

<strong> </strong>Write a class Airport. An airport has the following private fields:

<ul>

 <li>An int indicating the x-coordinate of the airport on a world map with a scale to 1 km.</li>

 <li>An int indicating the y-coordinate of the airport on a world map with a scale to 1 km.</li>

 <li>An int indicating the airport fees (<em>in cents</em>) associated to this airport.</li>

</ul>

The class must also have the following public methods:

<ul>

 <li>A constructor that takes three int as input indicating the position of the airport on a map (x and y coordinate) and the fees of the airport (in cents) respectively. The constructor uses the inputs to initialize the corresponding fields.</li>

 <li>A getFees method to retrieve the fees of the airport.</li>

 <li>A static method getDistance which takes as input two airport and returns a integer indicating the distance in kilometer between the two airports. Note that the method should <strong>round the distance up </strong>(e.g. both 5<em>.</em>9 and 5<em>.</em>2 should become 6). More over, remember that given two points (<em>x</em><sub>1</sub><em>,y</em><sub>1</sub>) and (<em>x</em><sub>2</sub><em>,y</em><sub>2</sub>), the distance can be computed with the following formula:</li>

</ul>

<em>distance </em>= <sup>p</sup>(<em>x</em><sub>1 </sub>− <em>x</em><sub>2</sub>)<sup>2 </sup>+ (<em>y</em><sub>1 </sub>− <em>y</em><sub>2</sub>)<sup>2</sup>

<strong> </strong>Write a class Room. An room has the following private fields:

<ul>

 <li>A String indicating the type of the room.</li>

 <li>An int indicating the price (in cents) of the room.</li>

 <li>A boolean indicating whether or not the room is available.</li>

</ul>

The class must also have the following public methods:

<ul>

 <li>A constructor that takes as input the type of the room and uses it to initialize the fields. Note that there are only 3 type of rooms supported by the program: <em>double</em>, <em>queen</em>, and <em>king</em>. If the input does not match one of these room type, then the constructor should throw an IllegalArgumentException explaining that no room of such type can be created. The price of the room is based on its type as follows: $90 for a double, $110 for a queen, $150 for a king. Remember that the price should be stored in cents. The constructor should set the availability for a new room to be true.</li>

 <li>A constructor that takes a Room as input and creates a copy of the input room (i.e. it initialize the fields using the values from the corresponding fields of the input room).</li>

 <li>A getType and a getPrice method which return the type and the price of the room respectively.</li>

 <li>A changeAvailability method which takes no input and sets the value stored in the availability field to be the opposite of the one currently there.</li>

 <li>A static method findAvailableRoom which takes as input an array of Rooms as well as a String indicating a room type. The method should return the <em>first </em>available room in the array of the indicated type. If no such room exists (either because all rooms of said type are occupied, or because no room of such type is in the array), the method returns null. <strong>Note that, no changes to any of the rooms in the input array should be made by this method!</strong></li>

 <li>A static method makeRoomAvailable which takes as input an array of Rooms as well as a String indicating a room type. The method should make the <em>first </em>unavailable room in the array of the indicated type available again. If successful, the method should return true, otherwise the method should return false.</li>

</ul>

<strong> </strong>Write a class Hotel. An hotel has the following private fields:

<ul>

 <li>An String indicating the name of the hotel.</li>

 <li>An array of Rooms indicating the rooms in the hotel.</li>

</ul>

The class must also have the following public methods:

<ul>

 <li>A constructor that takes a String and an array of Rooms respectively. The constructor uses the inputs to initialize the corresponding fields. Note that the array used to initialize the field representing the rooms should be a <em>deep copy </em>of the input array.</li>

 <li>A reserveRoom method which takes as input a String indicating the type of room to reserve. The method changes the availability of the first available room of the specified type in the hotel. If successful, the method returns the price of the room. Otherwise, an IllegalArgumentException should be thrown.</li>

 <li>A method cancelRoom which takes as input a String indicating the type of room to cancel. The method makes a room of that type available again. It returns true if it operation was possible, false</li>

</ul>

<strong> </strong>Write an abstract class Reservation which has the following private field:

<ul>

 <li>A String name</li>

</ul>

The class must also have the following public methods:

<ul>

 <li>A constructor that takes a String as input indicating the name of the client on the reservation and uses it to initialize the corresponding field.</li>

 <li>A final reservationName method to retrieve the name on this reservation.</li>

 <li>An abstract method getCost which takes no input and returns an int. This method should be abstract (thus, not implemented) because how to determine the cost depends on the type of reservation.</li>

 <li>An abstract method equals which takes an Object as an input and returns a boolean. This method should be abstract as well, since depending on the type of reservation different conditions should be met in order for two reservations to be considered equal.</li>

</ul>

<strong> </strong>All of the followings must be subclasses of Reservation:

<ul>

 <li>Write a class FlightReservation derived from the Reservation This class has the following private fields:

  <ul>

   <li>An Airport indicating the place of departure.</li>

   <li>An Airport indicating the place of arrival.</li>

  </ul></li>

</ul>

The class has also the following public methods:

<ul>

 <li>A constructor that takes as input a String with the name on the reservation, and two Airports indicating the place of departure and arrival respectively. The constructor uses the inputs to create a Reservation and initialize the corresponding fields. Throw an IllegalArgumentException if the two input airports are the same. Ignore the fact that you did not overrode the equals method in the Airport</li>

 <li>A getCost method that takes no input and returns the cost of the reservation (an int) in cents. The cost is computed adding together the fuels cost, the aiports fees, and $53.75 (which include costs related to the plane plus taxes). You can assume that <a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>:</li>

</ul>

∗ Planes pay $1.24 per gallon of fuel.

∗ Planes can fly 167.52 kilometer per gallon of fuel.

The cost should be <strong>rounded up </strong>to the nearest cent. For example, if after the computation above you obtain a flight cost of 103568<em>.</em>21187 cents, the method should return 103569 cents instead. You may assume that the cost of all reservations fits within an int and therefore doesn’t cause overflow.

<ul>

 <li>An equals method which takes as input an Object and return true if input matches this in type, name, and airports. Otherwise the method returns false. You can ignore the fact that you did not overrode the equals method in the Airport</li>

</ul>

<ul>

 <li>Write a class HotelReservation derived from the Reservation This class has the following private fields:

  <ul>

   <li>An Hotel indicating where to make the reservation.</li>

   <li>A String indicating the type of room to reserve.</li>

   <li>An int indicating the number of nights to be spent in the hotel.</li>

   <li>An int indicating the price (in cents) for one night in a room of the specified type in the specified hotel.</li>

  </ul></li>

</ul>

The class has also the following public methods:

<ul>

 <li>A constructor that takes as input a String with the name on the reservation, a Hotel, a String with the room type, and an int indicating the number of nights. The constructor uses the inputs to create a Reservation and initialize the corresponding fields. The constructor should also make sure to reserve a room of the correct type in the specified hotel. If such reservation is not possible, then an IllegalArgumentException should be raised.</li>

 <li>A getNumOfNights method to retrieve the number of night on the reservation.</li>

 <li>A getCost method that takes no input and returns the cost of the reservation (an int) in cents. The cost represents the price to pay for the specified type of room given the number of nights indicated in the reservation.</li>

 <li>An equals method which takes as input an Object and return true if input matches this in type, name, hotel, room type, number of nights, and total cost. Otherwise the method returns false. Once again, you can ignore the fact that you did not overrode the equals method in the Hotel</li>

</ul>

<ul>

 <li>Write a class BnBReservation derived from the HotelReservation This class has no fields, but it has the following public methods:

  <ul>

   <li>A constructor that takes as input a String with the name on the reservation, a Hotel, a String with the room type, and an int indicating the number of nights. The constructor uses the inputs to create an HotelReservation.</li>

   <li>A getCost method that takes no input and returns the cost of the reservation (an int) in cents. Since this reservation includes breakfast, to the cost of reserving the room in the hotel you should add $10 per night.</li>

  </ul></li>

</ul>

Write a class Basket representing a list of reservations. Note that the instructions on how to implement this class are not always very specific. This is intentional, since your assignment will not be tested on the missing details of the implementation. Note though, that your choices will make a difference in terms of how efficient your code will be. We will not be deducting point for inefficient code in Assignment 1. Note once again that, you are NOT allowed to import any other class (including ArrayList or LinkedList). The class has (at least) the following private field:

<ul>

 <li>An array of Reservation</li>

</ul>

The class must also have the following public methods:

<ul>

 <li>A constructor that takes no inputs and initialize the field with an array with no reservations.</li>

 <li>A getProducts method which takes no inputs and returns <em>a shallow copy </em>of the array of Reservations of the basket. This array should contain all the reservations in the basket in the same order in which they were added.</li>

 <li>An add method which takes as input a Reservation. The method adds the reservation <strong>at the end </strong>of the list of reservation of the basket and returns how many reservations are now there.</li>

 <li>A remove method which takes as input a Reservation and returns a boolean. The method removes the <strong>first </strong>occurrence of the specified element from the array of reservation of the basket. If no such reservation exists, then the method returns false, otherwise, after removing it, the method returns true. Note that this method removes <strong>a reservation from the list if and only if such reservation is </strong><em>equal </em><strong>to the input received</strong>. For example, two flight reservations from Montreal to Vancouver are not considered equal if they were created under two different names. After the reservation has been removed from the array, the subsequent elements should be shifted down by one position, <strong>leaving no unutilized slots in the middle array</strong>.</li>

 <li>A clear method which takes no inputs, returns no values, and empties the array of reservations of the basket.</li>

 <li>A getNumOfReservations method that takes no inputs and returns the number of reservations in the basket.</li>

 <li>A getTotalCost method that takes no inputs and returns the cost (in cents) of all the reservations in the basket.</li>

</ul>

Write a class Customer which has the following private fields:

<ul>

 <li>A String name</li>

 <li>An int representing the balance (in cents) of the customer</li>

 <li>A Basket containing the reservations the customer would like to make.</li>

</ul>

The class must also have the following public methods:

<ul>

 <li>A constructor that takes as input a String indicating the name of the customer, and an int representing their initial balance. The constructor uses its inputs and creates an empty Basket to initialize the corresponding fields.</li>

 <li>A getName and a getBalance method which return the name and balance (in cents) of the customer respectively.</li>

 <li>A getBasket method which returns the reference to the basket of the customer (no copy of the basket is needed).</li>

 <li>An addFunds method which takes an int as input representing the amount of cents to be added to the balance of the customer. If the input received is negative, the method should throw an IllegalArgumentException with an appropriate message. Otherwise, the method will simply update the balance and return the new balance in cents.</li>

 <li>An addToBasket method which takes a Reservation as input and adds it to the basket of the customer if the name on the reservation matches the name of the customer. If the method is successful it should return the number of reservations in the basket of this customer. Otherwise, the method should throw an IllegalArgumentException.</li>

 <li>An addToBasket method which takes a Hotel, a String representing a room type, an int representing the number of nights, and a boolean representing whether or not the customer wants breakfast to be included. The method adds the corresponding reservation to the basket of the customer and returns the number of reservations that are now in the basket of this customer.</li>

 <li>An addToBasket method which takes two Airports as input. The method adds the corresponding reservation to the basket of the customer and returns the number of reservations that are now in their basket, whether or not the flight reservation was created successfully.</li>

 <li>A removeFromBasket method which takes a Reservation as input and removes it from the basket of the customer. The method returns a boolean indicating whether of not the operation was successful.</li>

 <li>A checkOut method which takes no input. If the customer’s balance is not enough to cover the total cost of their basket, then the method throws an IllegalStateException. Otherwise, the customer is charged the total cost of the basket, <strong>the basket is cleared</strong>, and balance left is returned.</li>

</ul>


