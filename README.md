# venue_management_system

## Introduction
The Hall Booking Management System is a Java-based application developed for Hall Symphony Inc. to simplify the hall reservation process for customers. The system manages three types of halls: auditoriums (capacity: 1000), banquet halls (capacity: 300), and meeting rooms (capacity: 30). Business hours are 8:00 AM to 6:00 PM daily.

## Features

### User Types
- **Admin**: Manages staff and customer accounts, views bookings
- **Manager**: Tracks sales, assigns tasks, updates task progress
- **Scheduler**: Manages halls (add/edit/delete), schedules halls, views tasks
- **Customer**: Books halls, views bookings, sends feedback

### Core Functionality
- User authentication (login/logout)
- Profile management
- Hall booking and management
- Staff management
- Customer management
- Sales tracking
- Task assignment and progress tracking
- Feedback system

## System Design

### UML Diagrams

#### Use Case Diagram
![Image](https://github.com/user-attachments/assets/f69f3b88-7457-47c9-9e78-80585386a398)

The system includes use cases for:
- Customer operations (booking halls, viewing bookings, sending feedback)
- Admin operations (managing staff, viewing customers and bookings)
- Manager operations (viewing sales, assigning tasks)
- Scheduler operations (managing halls, scheduling maintenance)
- Common operations (login, updating profiles)

#### Class Diagram
![Image](https://github.com/user-attachments/assets/e2ffb074-2176-4dc5-90d9-3d3fe464d449)

Key classes include:
- **Manager**: Manages sales and task assignment
- **Scheduler**: Handles hall management and scheduling
- **Admin**: Manages staff and customers
- **Hall**: Represents bookable spaces
- **Schedule**: Manages dates and time slots
- **Booking**: Links customers, halls, and schedules
- **Customer**: Manages user accounts and booking functions
- **Sales**: Tracks financial transactions

## System Snippet 
![Image](https://github.com/user-attachments/assets/78a9027b-a9c3-4450-a665-9bf624828f93)

##Object-Oriented Concepts Used
###Constructor Overloading
Multiple constructors with different parameters to accommodate various initialization scenarios.

```java
// Example of constructor overloading
public Admin(String username, String admin_ID, String admin_name, String password) {
    this.username = username;
    this.admin_ID = admin_ID;
    this.admin_name = admin_name;
    this.password = password;
}

public Admin(String admin_ID) {
    this.admin_ID = admin_ID;
}

public Admin() {
}
```

### Encapsulation
Private fields with public getters and setters to control access to data.

```java
private String username;
private String admin_ID;
private String admin_name;
private String password;

public String getUsername() {
    return username;
}

public void setUsername(String username) {
    this.username = username;
}
```

### Abstraction (Interface)


Interface implementation to standardize functionality across classes.

```java
public interface super_class {
    public void showItems(JTable table);
}
```

### Polymorphism
Different implementations of the same method in different classes.
```java
// In Scheduler class
@Override
public void showItems(JTable table) {
    // Scheduler-specific implementation
}

// In Admin class
@Override
public void showItems(JTable table) {
    // Admin-specific implementation
}
```

### Inheritance
Extending base classes to create specialized functionality.
```java
// Override displayInfo to include role
    @Override
    public void displayInfo() {
        super.displayInfo(); // Call base class method
        System.out.println("Role: " + role);
    }
```
## Limitations
1. Data stored in text files rather than a database
2. No booking cancellation functionality
3. Limited to a single admin account
4. Users cannot update their personal information
5. No card validation system
6. Admin accounts cannot be blocked
7. Sales information cannot be edited

## Data Storage
The application uses text files for data storage:
- admin.txt
- scheduler.txt
- manager.txt
- customer.txt
- schedule.txt
- hall.txt
- bookings.txt
- feedbacks.txt

## Assumptions
1. Manager and scheduler work in the same office
2. Task progress is reported verbally
3. Only one admin account is permitted
4. No refunds are available for payments
5. Bookings cannot be canceled
6. Customers provide accurate information during sign-up

## Installation and Setup
Download the zip file and run the file.
