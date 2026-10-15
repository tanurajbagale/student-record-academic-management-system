# Algorithms and Pseudocode

## 1. Add student
**Algorithm**
1. Read the roll number.
2. Convert it into a tuple key.
3. If the key already exists, show a duplicate message and stop.
4. Read required profile details, subjects, marks, attendance, and clubs.
5. Validate marks and attendance.
6. Store the profile dictionary using the tuple key.
7. Update the sets of departments, subjects, and clubs.
8. Show success.

**Pseudocode**
```
BEGIN
  INPUT roll_number
  key ← TUPLE(roll_number)
  IF key exists in students THEN
      DISPLAY "Duplicate roll number"
      STOP operation
  ENDIF
  INPUT student details, subjects, marks, attendance, clubs
  VALIDATE marks are between 0 and 100
  VALIDATE attendance is between 0 and 100
  students[key] ← profile dictionary
  ADD department to departments set
  ADD subjects to subjects set
  ADD clubs to clubs set
  DISPLAY success
END
```

## 2. Search student
```
BEGIN
  INPUT roll_number
  key ← TUPLE(roll_number)
  IF key exists in students THEN
      DISPLAY students[key]
  ELSE
      DISPLAY "Student record not found"
  ENDIF
END
```

## 3. Update student
```
BEGIN
  INPUT roll_number
  FIND profile using tuple key
  IF profile does not exist THEN DISPLAY not found; STOP
  FOR each editable field
      INPUT new value
      IF new value is not empty THEN update field
  ENDFOR
  IF user chooses to update marks THEN validate and replace marks
  IF user chooses to update subjects THEN replace subject list
  DISPLAY success
END
```

## 4. Delete student
```
BEGIN
  INPUT roll_number
  key ← TUPLE(roll_number)
  IF key exists THEN DELETE students[key]; DISPLAY success
  ELSE DISPLAY not found
  ENDIF
END
```

## 5. Display records
```
BEGIN
  IF students is empty THEN DISPLAY no records
  ELSE FOR each profile in students
       DISPLAY profile fields and average marks
  ENDFOR
  ENDIF
END
```

## 6. Calculate overall average
```
BEGIN
  COLLECT all marks from all student profiles
  IF no marks exist THEN DISPLAY no marks; STOP
  average ← SUM(all marks) / COUNT(all marks)
  DISPLAY average
END
```

## 7. Find highest scorer
```
BEGIN
  FOR each student with marks
      calculate that student's average
  ENDFOR
  SELECT student with maximum average
  DISPLAY student's name, roll number, and average
END
```

## 8. List by department
```
BEGIN
  INPUT department
  FIND profiles whose department matches (case-insensitive)
  IF none found THEN DISPLAY no students found
  ELSE DISPLAY roll number and name for each match
  ENDIF
END
```

## 9. Count students and generate report
```
BEGIN
  DISPLAY COUNT(students)
  DISPLAY unique departments, subjects, and clubs
  CALCULATE overall average and highest scorer if records exist
  GROUP students by department and display names
END
```
