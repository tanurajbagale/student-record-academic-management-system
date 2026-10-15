# Problem Analysis and Data Structure Selection

## 1. Problem understanding
A student record system needs to store and manage student identity, contact information, department, subjects, marks, attendance, and clubs. It should support adding, searching, updating, deleting, displaying, and reporting records.

## 2. Inputs
- Roll number and registration number
- Student name, department, date of birth
- Address, email ID, and contact number
- Subject names and marks
- Attendance percentage and optional club names
- Menu choice and search/update/delete criteria

## 3. Outputs
- Confirmation or error messages
- Individual or all student profiles
- Overall average marks and highest scorer
- Students grouped/listed by department
- Total student count and summary report

## 4. Relationships
Each roll number identifies one student profile. Each profile contains multiple subjects and marks, contact details, attendance, and optional clubs. A department may contain many students; subjects and clubs may be shared by many students.

## 5. Data structure selection
- **Strings:** names, departments, email, address, phone, date of birth.
- **Lists:** subjects, marks, attendance entries, and club names because they hold ordered items.
- **Tuples:** a tuple is used as the student dictionary key derived from the roll number. Tuples are immutable.
- **Sets:** department, subject, and club catalogues to avoid duplicate values.
- **Dictionaries:** each student profile stores named fields; the main dictionary enables quick lookup by roll-number key.

## 6. Assumptions
- Roll number is unique.
- Marks are numbers from 0 to 100.
- Attendance is a percentage from 0 to 100.
- This learning version keeps records in memory only.
- Sample data in the README is fictional.
