# Testing Report

## Test environment
- Language: Python 3
- Dependencies: None
- Test type: manual testing and dry-run review

## Test cases

| ID | Test | Input/Action | Expected result |
|---|---|---|---|
| TC-01 | Empty database | Select Display All before adding records | “No student records available.” |
| TC-02 | Add valid record | Enter complete valid sample data | Record added successfully |
| TC-03 | Duplicate roll number | Add a second record with the same roll number | Duplicate message; existing record unchanged |
| TC-04 | Search existing | Search roll number 101 after adding it | Profile displayed |
| TC-05 | Search missing | Search roll number 999 | Record not found |
| TC-06 | Invalid marks | Enter a mark greater than 100 or below 0 | Validation message and re-entry |
| TC-07 | Non-numeric marks | Enter text instead of marks | Validation message and re-entry |
| TC-08 | Invalid attendance | Enter attendance above 100 | Validation message and re-entry |
| TC-09 | Update record | Update an existing student's name | New name displayed |
| TC-10 | Delete record | Delete an existing student's roll number | Record deleted; later search reports not found |
| TC-11 | Average | Enter marks 78, 85, 91 | Average = 84.67 |
| TC-12 | Highest scorer | Add two students with different average marks | Student with the greater average is displayed |
| TC-13 | Department filter | Search department “AI & ML” | Matching students listed, ignoring case |
| TC-14 | Invalid menu choice | Enter 99 | Invalid choice message |
| TC-15 | Exit | Select 0 | Program exits with thank-you message |

## Observations
The design rejects duplicate roll numbers and invalid numeric ranges for marks and attendance. Searching uses a tuple key in the main dictionary. Sets maintain unique catalogue entries. Records are not saved between runs.

## Evidence/screenshots
Run the program and capture screenshots showing:
1. Main menu.
2. A successfully added fictional student.
3. Search/display result.
4. Academic report.
5. Invalid marks or duplicate roll-number validation.

Add your own screenshots here before submission. Do not claim screenshots have been captured if they have not.
