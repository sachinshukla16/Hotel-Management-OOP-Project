# Hotel-Management-OOP-Project

This project is a console-based Hotel Management System implemented in Java. It provides a menu-driven interface for managing various hotel operations, including room booking, customer details, food ordering, and checkout, with data persistence.

Here's a breakdown of the project's structure and functionality, followed by key points for your resume:

Project Explanation:
The project is structured using several Java classes, each responsible for a specific aspect of the hotel management:

Food Class:

Represents a food item with itemno, quantity, and calculated price.

It's Serializable to allow saving food order details.

Singleroom Class:

Represents a single occupancy room, storing name, contact, gender of the customer, and an ArrayList of Food items ordered.

It's Serializable for persistence.

Doubleroom Class:

Extends Singleroom, adding fields for a second customer (name2, contact2, gender2).

Represents double occupancy rooms.

It's also Serializable.

NotAvailable Class:

A custom Exception class thrown when a user attempts to book an already occupied room.

holder Class:

Acts as a central data container for the entire hotel.

It holds arrays of Doubleroom (luxury and deluxe) and Singleroom (luxury and deluxe) objects, effectively representing all the rooms in the hotel.

This class is Serializable, enabling the entire hotel's state to be saved and loaded.

Hotel Class:

Contains static methods that implement the core business logic of the hotel management system.

CustDetails(int i, int rn): Collects customer information and assigns it to a specific room.

bookroom(int i): Guides the user through selecting and booking an available room. It checks for availability and utilizes the NotAvailable custom exception.

features(int i): Displays details (beds, AC, breakfast, daily charge) for different room types.

availability(int i): Shows the count of available rooms for each type.

bill(int rn, int rtype): Calculates and displays the total bill for a room, including room charges and food costs.

deallocate(int rn, int rtype): Handles the checkout process, displaying the bill and making the room available again.

order(int rn, int rtype): Presents a food menu and allows customers to order items, which are then added to their room's food list.

write Class:

Implements the Runnable interface, allowing it to be executed in a separate thread.

Its run() method is responsible for serializing (saving) the holder object (which contains all hotel data) to a file named "backup". This ensures data persistence.

Main Class:

The primary class containing the main method, which is the application's entry point.

Data Loading: On startup, it checks for the "backup" file. If found, it deserializes (loads) the previous hotel state from this file, so no data is lost between program runs.

Menu Interface: Presents a loop-driven menu to the user, allowing them to choose various operations (display room details, availability, book, order food, checkout, exit).

User Interaction: Takes user input via Scanner and calls the appropriate static methods from the Hotel class.

Data Saving (on exit): Before exiting, it creates and starts a new Thread using the write class to save the current hotel state to the "backup" file.

Error Handling: Includes try-catch blocks for general exceptions and specific handling for invalid room numbers.

Key Concepts and Technologies Demonstrated:
Object-Oriented Programming (OOP): Extensive use of classes (Food, Singleroom, Doubleroom, Hotel, etc.), objects, inheritance (Doubleroom extends Singleroom), and encapsulation.

Data Structures: Utilizes ArrayList for dynamic food order lists and arrays for managing different room types.

File Handling & Persistence: Implements Serializable for objects and uses FileInputStream, FileOutputStream, ObjectInputStream, ObjectOutputStream for saving and loading the entire application state to/from a file.

Multithreading: Leverages the Runnable interface and Thread class to perform file writing in a separate thread, enhancing application responsiveness.

Exception Handling: Implements try-catch blocks for robust error management, including a custom exception (NotAvailable) for specific business logic scenarios.

Console-based User Interface: Develops a menu-driven interactive system using Scanner for input and System.out.println for output.

Key Points:

Developed a comprehensive Hotel Management System in Java, applying core Object-Oriented Programming (OOP) principles like inheritance, encapsulation, and polymorphism for modular design.

Implemented robust data persistence using Java Object Serialization to save and restore the entire hotel state (room bookings, customer details, and food orders) to/from a file, ensuring data integrity across sessions.

Utilized multithreading to perform asynchronous file I/O operations, enhancing application responsiveness and user experience during data saving.

Designed and managed a diverse set of room types (Luxury/Deluxe, Single/Double) with distinct features and pricing, demonstrating effective data modeling and system logic.

Engineered a menu-driven console interface, providing functionalities for room booking, availability checks, customer management, food ordering, detailed billing, and room deallocation.

Incorporated custom exception handling (NotAvailable exception) to gracefully manage specific business rule violations and improve application stability.

Gained practical experience with Java's I/O streams (FileInputStream, FileOutputStream, ObjectInputStream, ObjectOutputStream) for efficient file manipulation.
