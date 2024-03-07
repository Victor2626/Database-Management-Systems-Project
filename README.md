# Zoo Management Database Project

## Overview
This database represents a comprehensive management model for a zoo, utilizing a relational structure composed of interconnected tables through primary and foreign keys. This architecture allows for efficient storage and management of data related to various aspects of zoo operations including the zoo itself, employees, animals, species, cages, locations, shows, tickets, connections, visitors, scheduling, care, employment, and visitation.

## Database Structure

### `ZOO_GARDEN` Table:
- Contains information about the zoo, such as its size and the city it is located in. 
- Relationships: 
  - One to many with `EMPLOYMENT`, `ANIMAL`, and `SHOW` tables.
  - Many to one with `SCHEDULE`.
  - One to many with `VISITATION`.

### `EMPLOYEE` Table:
- Stores details about zoo employees including name, first name, age, gender, and salary.
- Relationships: 
  - One to many with `EMPLOYMENT` and `CARE` tables.

### `ANIMAL` Table:
- Holds data on zoo animals, such as their category, number, and names.
- Relationships: 
  - Many to one with `ZOO_GARDEN`.
  - One to many with `CONNECTION` and `CARE`.
  - Many to one with `SPECIES`.

### `TICKET` Table:
- Details about tickets for zoo shows, including price and category.
- Relationship: 
  - Many to one with `SHOW`.

### `SHOW` Table:
- Information on zoo shows, such as maximum number of seats.
- Relationships: 
  - One to many with `TICKET` and `CONNECTION`.
  - Many to one with `ZOO_GARDEN`.

### `CONNECTION` Table:
- Facilitates the link between `ANIMAL` and `SHOW` tables to manage many-to-many relationships as one to many from `CONNECTION` to `ANIMAL`, and one to many from `SHOW` to `CONNECTION`.

### `SPECIES` Table:
- Data about animal species, including breed and number of families.
- Relationship: 
  - One to many with `ANIMAL`.

### `CAGE` Table:
- Information on animal cages, like material and size.
- Relationships: 
  - Many to one with `LOCATION`.
  - One to many with `CARE`.

### `LOCATION` Table:
- Stores details about locations within the zoo where each cage is placed, including their positions and distance from the entrance.
- Relationship: 
  - One to many with `CAGE`.

### `VISITOR` Table:
- Data on zoo visitors, such as their age category.
- Relationship: 
  - One to many with `VISITATION`.

### `SCHEDULE` Table:
- Information on the zoo's operational hours, including days of the week, opening, and closing times.
- Relationship: 
  - One to many with `ZOO_GARDEN`.

### `CARE` Table:
- Links `ANIMAL`, `EMPLOYEE`, and `CAGE` tables to manage many-to-many relationships as one to many between each pair (i.e., `EMPLOYEE` to `CARE`, `CAGE` to `CARE`, and `ANIMAL` to `CARE`).

### `VISITATION` Table:
- Manages the link between `VISITOR` and `ZOO_GARDEN` tables to handle many-to-many relationships as one to many from `VISITATION` to `VISITOR`, and one to many from `ZOO_GARDEN` to `VISITATION`.

### `EMPLOYMENT` Table:
- Manages the relationship between `EMPLOYEE` and `ZOO_GARDEN` tables to simplify many-to-many connections as one to many from `EMPLOYMENT` to `EMPLOYEE`, and one to many from `ZOO_GARDEN` to `EMPLOYMENT`.

## Implementation Details
The database's relational model ensures robust data integrity and efficient access patterns. Primary and foreign keys facilitate the linkage between tables, allowing for complex queries and reports necessary for effective zoo management. This model supports operations such as tracking animal health, employee scheduling, ticket sales analysis, and visitor management, among others.

## Conclusion
The Zoo Management Database Project leverages a relational database structure to offer a comprehensive solution for managing the intricate details of zoo operations. Through its well-defined tables and relationships, the database provides a solid foundation for storing, retrieving, and analyzing zoo-related data efficiently.
