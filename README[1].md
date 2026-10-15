# Student Record and Academic Management System
## Data Organization Using Python Collections

**Project type:** First-year Python programming assignment  
**Language:** Python 3  
**Main file:** `student_management.py`

## Objective
To use Python strings, lists, tuples, sets, and dictionaries to store, organize, update, search, and report student academic information.

## Features
- Add, search, update, and delete student records
- Display all student profiles
- Calculate overall average marks
- Find the highest scorer using each student's average marks
- List students by department
- Count students and display known departments, subjects, and clubs
- Generate a simple academic report
- Validate empty fields, duplicate roll numbers, marks, attendance, and menu choices

## Data structures used
| Data structure | Use in this project |
|---|---|
| String | Names, department, address, email, phone |
| List | Subjects, marks, attendance list, club names |
| Tuple | Roll-number key and registration/date fields are represented as profile values; roll-number key is a tuple |
| Set | Unique departments, subjects, and student clubs |
| Dictionary | Complete student profile and the main student-record lookup |

## Requirements
Python 3.8 or later. No external packages are required.

## Run the program
1. Download or clone this repository.
2. Open a terminal in the project folder.
3. Run:

```bash
python student_management.py
```

On some systems, use `python3 student_management.py`.

## Suggested test data
- Roll number: 101
- Registration number: SU2026-101
- Name: Asha Patil
- Department: AI & ML
- Date of birth: 12-05-2008
- Address: Kopargaon
- Email: asha@example.com
- Contact number: 9876543210
- Subjects: Python, Mathematics, Physics
- Marks: 78, 85, 91
- Attendance: 92
- Clubs: Coding Club, Dance Club

Use fictional sample data for screenshots. Do not upload real student contact information.

## Project documents
- `docs/problem_analysis.md` — problem statement and data selection
- `docs/algorithms_pseudocode.md` — algorithms and pseudocode
- `docs/flowcharts.md` — flowcharts in Mermaid syntax
- `docs/testing_report.md` — test cases and observations
- `docs/project_documentation.md` — implementation notes and conclusion

## Limitations
Records are held in memory and will be cleared when the program exits. Persistent storage, authentication, and a graphical interface are not included because the assignment focuses on Python collections.

## Author
Student name: **[Enter your name]**  
PRN: **[Enter your PRN]**  
Course: **B.Tech AI & ML, First Year**  
University: **Sanjivani University**
