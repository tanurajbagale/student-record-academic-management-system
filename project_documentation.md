# Project Documentation

## Title
Student Record and Academic Management System – Data Organization using Python Collections

## Introduction
This project demonstrates how Python collections can be combined to manage student academic information. It is a menu-driven command-line application.

## Objectives
- Store and organize student information.
- Practice strings, lists, tuples, sets, and dictionaries.
- Implement add, search, update, delete, and display operations.
- Calculate average marks and identify the highest scorer.
- Filter students by department and generate a summary report.
- Test common valid and invalid inputs.

## Modules/functions
- `add_student()` — reads and stores a student profile.
- `search_student()` — looks up a profile by roll number.
- `update_student()` — updates selected fields.
- `delete_student()` — removes a profile.
- `display_all_students()` — prints all profiles.
- `calculate_average()` — calculates the average of all stored marks.
- `highest_scorer()` — finds the student with the highest individual average.
- `list_by_department()` — filters profiles by department.
- `count_students()` and `generate_report()` — display collection summaries and academic information.
- `main()` — repeats the menu until the user exits.

## Data organization
The main `students` dictionary maps a tuple made from the roll number to a profile dictionary. Profile fields include strings, subject/marks lists, and club lists. Sets hold unique department, subject, and club names.

## Testing
Refer to `testing_report.md`. Execute the listed test cases and record actual results/screenshots before submitting.

## Conclusion
The project integrates Python collections into one practical student-record application. It illustrates how each data structure has a different purpose and how input validation improves reliability.

## Student details
- Name: [Enter your name]
- PRN: [Enter your PRN]
- Class/Division: [Enter your class/division]
- Subject: Python Programming
- University: Sanjivani University
