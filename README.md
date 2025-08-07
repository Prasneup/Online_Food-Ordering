1. Main Class

FoodOrderingSystemWithPayment.java

Entry point of the application.
Contains the main method to initialize the restaurant, customer, and order flow.
Manages user interactions via a menu-driven interface.



2. Core Entities

Customer.java

Represents a customer with attributes: name, phone, address, and wallet.
Includes a default wallet with an initial balance (Rs. 500).


Restaurant.java

Manages the restaurant's menu (list of MenuItem objects).
Provides methods to add items and display the menu by category.


MenuItem.java

Defines a menu item with name, price, and category.
Includes a toString method for display.



3. Order Management

Order.java

Represents an order with orderId, customer, items, orderTime, deliveryCharge, payment, and status.
Methods: addItem, calculateSubtotal, calculateTotal, processPayment, printReceipt, and displayItems.


OrderItem.java

Represents an item in the order with menuItem and quantity.
Calculates subtotal and provides a toString method.


OrderStatus.java

Enum defining order states: PENDING, CONFIRMED, PREPARING, OUT_FOR_DELIVERY, DELIVERED, CANCELLED.



4. Payment System

Payment.java

Abstract base class for payments with paymentId, amount, timestamp, and status.
Defines the abstract processPayment method.


PaymentStatus.java

Enum for payment states: PENDING, SUCCESS, FAILED, REFUNDED.


PaymentMethod.java

Enum for payment types: WALLET, CARD, UPI, CASH_ON_DELIVERY.


WalletPayment.java

Extends Payment for wallet-based payments, checking balance and updating it.


CardPayment.java

Extends Payment for card payments with simulated 95% success rate.


UPIPayment.java

Extends Payment for UPI payments with simulated 90% success rate.


CashOnDeliveryPayment.java

Extends Payment for cash on delivery with immediate success.


PaymentProcessor.java

Static method createPayment to instantiate the appropriate payment type.


Wallet.java

Manages balance and transactionHistory with methods to add/deduct balance and show history.



5. Utility Classes

PaymentProcessor.java (shared with Payment System)

Handles payment creation logic.



File Organization
All .java files are located in the root directory of the repository. Compile and run using:

javac *.java
java FoodOrderingSystemWithPayment

This structure ensures modularity and scalability, making it easy to extend or debug the system.

Notes

Placement: Add this section under a suitable heading like Project Structure or Code Overview in your README.md.
Customization: You can adjust the descriptions or add more details (e.g., method lists) if needed.
Visual Appeal: Use Markdown headers (#, ##, ###) and bullet points for clarity, as shown above.

