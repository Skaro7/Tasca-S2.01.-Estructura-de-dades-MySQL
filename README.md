# Entity-Relationship Diagrams – Database Modeling (Level 1)

## 📄 Description

This task focuses on designing **Entity-Relationship (ER) diagrams** to model real-world business scenarios and translate functional requirements into structured database designs.

You will model two different systems:

* An **optical shop management system**
* A **pizza delivery ordering system**

The goal is to identify:

* Entities and attributes
* Relationships between entities
* Cardinalities (one-to-one, one-to-many, many-to-many)
* Business rules that affect database structure

This exercise strengthens your ability to think in terms of **relational modeling** and prepares you for designing normalized databases.

---

## 💻 Technologies Used

* Database modeling concepts
* Entity-Relationship (ER) diagrams
* Relational database design
* Any ER diagram tool (draw.io, Lucidchart, MySQL Workbench, etc.)

---

## 📋 Requirements

To complete this project, you will need:

* Basic knowledge of relational databases
* An ER diagram design tool or paper sketching
* Understanding of:
    * Primary keys
    * Foreign keys
    * Cardinalities
    * Normalization

---

## 🛠️ Installation

This is a **design-only project**. No code installation is required.

If using a diagram tool:

1. Open your preferred ER modeling tool.
2. Create a new diagram file.
3. Start modeling the entities and relationships described below.

---

## ▶️ Execution

There is no program execution for this task.

The deliverable is:

* One or more **ER diagrams** representing:
    * Exercise 1 – Optical Shop
    * Exercise 2 – Pizzeria

---

## 🧩 Level 1 – Exercises

---

## 🧪 Exercise 1 – Optical Shop (“Cul d'Ampolla”)

Design an ER diagram to manage customers and glasses sales for an optical shop.

### Supplier (Proveïdor)

Store the following attributes:

* Name
* Address:
    * Street
    * Number
    * Floor
    * Door
    * City
    * Postal code
    * Country
* Phone
* Fax
* NIF

Business rule:

* Each **brand** of glasses is purchased from **one single supplier**.
* A supplier can provide **many brands**.

---

### Glasses (Ulleres)

Store:

* Brand
* Left lens graduation
* Right lens graduation
* Frame type:
    * Floating
    * Plastic
    * Metal
* Frame color
* Left lens color
* Right lens color
* Price

Relationships:

* Each pair of glasses belongs to **one supplier**.
* Each sale is associated with:
    * One **customer**
    * One **employee**

---

### Customer (Client)

Store:

* Name
* Postal address
* Phone
* Email
* Registration date
* Recommended by:
    * Another customer (optional self-relationship)

---

### Employee (Empleat)

* Identify which employee sold each pair of glasses.

---

### Key Relationships

* Supplier → Glasses (1:N)
* Customer → Glasses/Sales (1:N)
* Employee → Glasses/Sales (1:N)
* Customer → Customer (self-relationship for recommendations)

---

## 🧪 Exercise 2 – Pizzeria Ordering System

Design an ER diagram for an online food ordering platform.

---

### Customer

Store:

* Customer ID
* Name
* Surname
* Address
* Postal code
* Phone
* Locality (FK)

Relationships:

* One customer can place **many orders**.
* Each order belongs to **one customer**.

---

### Locality and Province

Store in separate tables:

#### Province

* Province ID
* Name

#### Locality

* Locality ID
* Name
* Province ID (FK)

Rules:

* One province has **many localities**.
* Each locality belongs to **one province**.

---

### Order (Comanda)

Store:

* Order ID
* Date and time
* Delivery type:
    * Home delivery
    * Store pickup
* Total price
* Store ID (FK)

Relationships:

* One order belongs to:
    * One customer
    * One store
* One order contains:
    * One or more products

---

### Product

Store:

* Product ID
* Name
* Description
* Image
* Price

Product types:

* Pizza
* Hamburger
* Drink

Relationships:

* Orders ↔ Products (Many-to-Many)
    * Include quantity per product in the relationship table.

---

### Pizza Categories

Store:

* Category ID
* Name

Rules:

* One pizza belongs to **one category**.
* One category can contain **many pizzas**.

---

### Store (Botiga)

Store:

* Store ID
* Address
* Postal code
* Locality
* Province

Relationships:

* One store manages **many orders**.
* One store employs **many employees**.

---

### Employee (Empleat)

Store:

* Employee ID
* Name
* Surname
* NIF
* Phone
* Role:
    * Cook
    * Delivery person

Delivery-specific data:

* For home delivery orders, store:
    * Delivery employee
    * Delivery date and time

---

## 🧠 Key Concepts Practiced

* Entity identification
* Attribute definition
* Primary and foreign keys
* One-to-many and many-to-many relationships
* Self-relationships
* Normalization principles
* Translating business rules into data models

---

## 🌐 Deployment

This is a **database design project** and does not require deployment.

The final result should be:

* ER diagrams saved as images or PDF
* Clear representation of:
    * Entities
    * Attributes
    * Relationships
    * Cardinalities

These diagrams can later be used to generate SQL schemas.
