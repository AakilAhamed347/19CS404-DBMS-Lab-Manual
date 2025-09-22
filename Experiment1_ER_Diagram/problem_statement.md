# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_fitness.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:


### Entities and Attributes

| Entity          | Attributes (PK, FK)                                                                          | Notes                                             |
| --------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| **Customer**    | **CustomerID (PK)**, Name, Phone, Email                                                      | Identifies customer making reservation or walk-in |
| **Reservation** | **ReservationID (PK)**, Date, Time, NoOfGuests, CustomerID (FK), TableID (FK), WaiterID (FK) | Links to customer, assigned table, and waiter     |
| **Table**       | **TableID (PK)**, TableNumber, Capacity, Location                                            | Restaurant tables with seating capacity           |
| **Waiter**      | **WaiterID (PK)**, Name, Phone, Shift                                                        | Waiter assigned to serve a reservation            |
| **Order**       | **OrderID (PK)**, ReservationID (FK), OrderTime                                              | Each reservation can have one or more orders      |
| **Order\_Dish** | **OrderDishID (PK)**, OrderID (FK), DishID (FK), Quantity                                    | Resolves many-to-many between Orders and Dishes   |
| **Dish**        | **DishID (PK)**, Name, Price, CategoryID (FK)                                                | Individual menu items                             |
| **Category**    | **CategoryID (PK)**, CategoryName (Starter/Main/Dessert/etc.)                                | Classification of dishes                          |
| **Bill**        | **BillID (PK)**, ReservationID (FK), FoodAmount, ServiceCharge, TotalAmount, BillDate        | Bill generated per reservation                    |


### Relationships and Constraints

| Relationship                   | Cardinality           | Participation             | Notes                                                                                                       |
| ------------------------------ | --------------------- | ------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Customer – Reservation         | 1\:M                  | Total on Reservation side | A customer can make many reservations; each reservation belongs to exactly one customer                     |
| Reservation – Table            | 1:1 (at a given time) | Total on Reservation side | Each reservation is assigned one table; each table can serve multiple reservations but not at the same time |
| Reservation – Waiter           | 1\:M                  | Total on Reservation side | One waiter can handle many reservations; each reservation is served by one waiter                           |
| Reservation – Order            | 1\:M                  | Total on Order side       | A reservation may have multiple orders                                                                      |
| Order – Dish (via Order\_Dish) | M\:N                  | Total on both sides       | Each order may contain multiple dishes, and each dish may appear in multiple orders                         |
| Dish – Category                | M:1                   | Total on Dish side        | Each dish belongs to one category, but a category has many dishes                                           |
| Reservation – Bill             | 1:1                   | Total on both sides       | Each reservation generates exactly one bill                                                                 |

### Assumptions
Customers may walk in without prior reservation, but once seated, a reservation record is still created.

Each reservation is linked to one table only (no combining tables in this version).

A bill is always generated per reservation, regardless of number of orders.

Service charge is a fixed percentage (e.g., 10%) applied on food total.

Waiters are assigned per reservation (not per dish or per order).

A dish always belongs to exactly one category.

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
