## Hospital Management System (HMS) Entity-Relationship Diagram (ERD)

# Table of Contents

# Project Overview

# Key Entities and Relationships

# Design Scope and Goal

# Design Decisions

# How to View the Diagram




# 1. Project Overview

This repository contains the Entity-Relationship Diagram (ERD) for a conceptual Hospital Management System (HMS). The diagram serves as the logical blueprint for a relational database, modeling the core data requirements for managing staff, departments, patients, and hospital locations.

This project was developed as a fundamental exercise in database design, aiming to achieve Third Normal Form (3NF) and ensure data integrity across all hospital operations.

Key Entities in the ER Diagram
# 1. Hospital Entity

Description: This entity represents the primary institution that hosts the system. It functions as the top-level entity to which all departments belong.



Primary Key: HospitalID.


Key Attributes: It tracks the official Name and general Info of the hospital. The Address is modeled as a Composite attribute, decomposed into atomic fields like City, State, and Pincode to facilitate structured queries.


Relationship: It has a One-to-Many (1:N) relationship with the Department entity.


# 2. Department (Dept) Entity

Description: Departments define the organizational units within the hospital, such as Cardiology, Emergency, or Radiology. This entity is crucial for connecting the hospital structure to the staff and patients.



Primary Key: DeptID.



Key Attributes: Key information includes the department's Name, Location, and InternalPhoneNo. It specifies the Type of department, such as 'Emergency', 'Inpatient', or 'OPD'.



Relationship: It links back to the Hospital via the HospitalID Foreign Key, and has a One-to-Many (1:N) relationship with the Doctor entity.



# 3. Doctor Entity

Description: This entity represents the medical professionals who treat patients and work within a specific department.


Primary Key: DoctorID.



Key Attributes: The doctor's Name is a Composite attribute (broken down into FName and LName). Other details include Designation and their medical Specialization (e.g., 'Pediatrics', 'Oncology'). The Contact No is modeled as a Multivalued attribute, handled in a separate table (Doctor_Phone) to comply with First Normal Form (1NF).



Relationship: It links to the Department via a Foreign Key (DeptID) and participates in a Many-to-Many (M:N) relationship with the Patient entity, which is resolved via a linking relationship like "Treat" or "Admitted".


# 4. Patient Entity

Description: This entity represents the individuals receiving care at the hospital and stores their biographical and basic clinical data.


Primary Key: MR_No (Medical Record Number).


Key Attributes: Both Name and Address are Composite attributes. Simple attributes include DateOfBirth, Gender, BloodType, a general History text field, and an alternative FileNo.


Relationship: It participates in the Many-to-Many (M:N) relationship with the Doctor entity, capturing treatment and admission records.

# 5. How to View the Diagram

The primary ER Diagram is available as an image file in this repository: Screenshot (110).jpg

You can view the full diagram directly in your browser. For any modifications, you will need a standard ER diagramming tool.

