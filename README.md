# Hospital Management System (HMS) Entity-Relationship Diagram (ERD)

## Table of Contents

# Project Overview

# Key Entities and Relationships

# Design Scope and Goal

# Design Decisions

# How to View the Diagram




# 1. Project Overview

This repository contains the Entity-Relationship Diagram (ERD) for a conceptual Hospital Management System (HMS). The diagram serves as the logical blueprint for a relational database, modeling the core data requirements for managing staff, departments, patients, and hospital locations.

This project was developed as a fundamental exercise in database design, aiming to achieve Third Normal Form (3NF) and ensure data integrity across all hospital operations.

# 2. Key Entities and Relationships

The ERD models the following primary entities:

Entity

Description

Key Relationships

Hospital

The central facility entity, linked to its physical location.

 1:M with Dept

# Dept (Department)

Organizational units (e.g., Emergency, Cardiology, ICU) within the hospital.

M:1 with Hospital, 1:M with Doctor

# Doctor

Medical professionals with specific specialties and contact details.

M:1 with Dept

# Patient

Individuals admitted or registered for services.

M:M with Doctor (via an implicit relationship entity in the diagram)

# Staff

Other non-doctor employees (e.g., nurses, administrative).

M:1 with Dept

# Core Relationships

Hospital to Department (1:M): One Hospital manages multiple Departments.

Department to Doctor (1:M): One Department employs multiple Doctors.

Doctor to Patient (M:M): A Doctor can treat multiple Patients, and a Patient can be treated by multiple Doctors (representing consultations/treatment episodes).

# 3. Design Scope and Goal

The primary goal of this ERD is to logically organize the data required for:

Staff and Resource Allocation: Tracking which doctors, staff, and departments belong to which hospital location.

Patient Identification: Capturing essential patient demographic and identification details (MR_No, Date of Birth, Gender, Address).

Organizational Structure: Modeling the internal structure of the hospital, separating departments into types (e.g., "Emergency," "Intensive Care," "Specialty Wards").

# 4. Design Decisions

Composite Attributes: Attributes like Address and Phone No are modeled as composite, recognizing that they are composed of several sub-attributes (e.g., City, Address Line 1, L.Name, F.Name).

Multivalued Attributes: Specialty/Wards is modeled to accommodate a Department having multiple types of specialty wards.

Partial Dependency: The diagram shows the decomposition of complex real-world relationships into simple, normalized structures for efficient querying and data maintenance.

# 5. How to View the Diagram

The primary ER Diagram is available as an image file in this repository: Screenshot (110).jpg

You can view the full diagram directly in your browser. For any modifications, you will need a standard ER diagramming tool.

