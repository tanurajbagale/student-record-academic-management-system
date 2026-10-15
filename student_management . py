"""
Student Record and Academic Management System
Uses strings, lists, tuples, sets, and dictionaries.
Run: python student_management.py
"""

from datetime import date

students = {}  # key: roll number tuple; value: student profile dictionary
departments = set()
subjects_catalog = set()
student_clubs = set()


def make_roll_key(roll_number):
    return (str(roll_number).strip(),)


def read_nonempty(prompt):
    while True:
        value = input(prompt).strip()
        if value:
            return value
        print("Input cannot be empty. Please try again.")


def read_marks():
    while True:
        raw = input("Enter marks separated by commas (e.g. 78, 85, 91): ").strip()
        try:
            marks = [float(item.strip()) for item in raw.split(",") if item.strip()]
            if not marks:
                raise ValueError
            if any(mark < 0 or mark > 100 for mark in marks):
                print("Marks must be between 0 and 100.")
                continue
            return marks
        except ValueError:
            print("Invalid marks. Enter numbers from 0 to 100, separated by commas.")


def add_student():
    print("\n--- Add Student ---")
    roll = read_nonempty("Roll number: ")
    key = make_roll_key(roll)
    if key in students:
        print("A student with this roll number already exists.")
        return

    reg_no = read_nonempty("Registration number: ")
    name = read_nonempty("Full name: ")
    department = read_nonempty("Department: ")
    dob = read_nonempty("Date of birth (DD-MM-YYYY): ")
    address = read_nonempty("Address: ")
    email = read_nonempty("Email ID: ")
    phone = read_nonempty("Contact number: ")
    subject_text = read_nonempty("Subjects separated by commas: ")
    subjects = [item.strip() for item in subject_text.split(",") if item.strip()]
    marks = read_marks()
    attendance = []

    while True:
        raw = input("Attendance percentage (0-100): ").strip()
        try:
            attendance_percent = float(raw)
            if 0 <= attendance_percent <= 100:
                break
            print("Attendance must be between 0 and 100.")
        except ValueError:
            print("Please enter a valid number.")

    club_text = input("Student clubs separated by commas (or press Enter for none): ").strip()
    clubs = [item.strip() for item in club_text.split(",") if item.strip()]

    students[key] = {
        "roll_number": roll,
        "registration_number": reg_no,
        "name": name,
        "department": department,
        "date_of_birth": dob,
        "address": address,
        "email": email,
        "phone": phone,
        "subjects": subjects,
        "marks": marks,
        "attendance": attendance,
        "attendance_percent": attendance_percent,
        "clubs": clubs,
    }
    departments.add(department)
    subjects_catalog.update(subjects)
    student_clubs.update(clubs)
    print("Student record added successfully.")


def display_student(profile):
    print("-" * 45)
    print(f"Roll Number       : {profile['roll_number']}")
    print(f"Registration No.  : {profile['registration_number']}")
    print(f"Name              : {profile['name']}")
    print(f"Department        : {profile['department']}")
    print(f"Date of Birth     : {profile['date_of_birth']}")
    print(f"Address           : {profile['address']}")
    print(f"Email             : {profile['email']}")
    print(f"Phone             : {profile['phone']}")
    print(f"Subjects          : {', '.join(profile['subjects'])}")
    print(f"Marks             : {profile['marks']}")
    print(f"Average Marks     : {sum(profile['marks']) / len(profile['marks']):.2f}")
    print(f"Attendance        : {profile['attendance_percent']:.2f}%")
    print(f"Clubs             : {', '.join(profile['clubs']) if profile['clubs'] else 'None'}")


def search_student():
    roll = read_nonempty("Enter roll number to search: ")
    profile = students.get(make_roll_key(roll))
    if profile:
        display_student(profile)
    else:
        print("Student record not found.")


def update_student():
    roll = read_nonempty("Enter roll number to update: ")
    profile = students.get(make_roll_key(roll))
    if not profile:
        print("Student record not found.")
        return
    print("Press Enter to keep the current value.")
    for field, prompt in [
        ("name", "Name"),
        ("department", "Department"),
        ("address", "Address"),
        ("email", "Email"),
        ("phone", "Phone"),
        ("date_of_birth", "Date of birth"),
    ]:
        value = input(f"{prompt} [{profile[field]}]: ").strip()
        if value:
            profile[field] = value
    if input("Update marks? (y/n): ").strip().lower() == "y":
        profile["marks"] = read_marks()
    if input("Update subjects? (y/n): ").strip().lower() == "y":
        raw = read_nonempty("Subjects separated by commas: ")
        profile["subjects"] = [item.strip() for item in raw.split(",") if item.strip()]
        subjects_catalog.update(profile["subjects"])
    departments.add(profile["department"])
    print("Student record updated successfully.")


def delete_student():
    roll = read_nonempty("Enter roll number to delete: ")
    key = make_roll_key(roll)
    if key in students:
        del students[key]
        print("Student record deleted successfully.")
    else:
        print("Student record not found.")


def display_all_students():
    if not students:
        print("No student records available.")
        return
    for profile in students.values():
        display_student(profile)


def calculate_average():
    if not students:
        print("No records available to calculate an average.")
        return
    all_marks = [mark for profile in students.values() for mark in profile["marks"]]
    if not all_marks:
        print("No marks are available.")
        return
    print(f"Overall average marks: {sum(all_marks) / len(all_marks):.2f}")


def highest_scorer():
    scored = [
        (sum(p["marks"]) / len(p["marks"]), p)
        for p in students.values() if p["marks"]
    ]
    if not scored:
        print("No marks are available.")
        return
    average, profile = max(scored, key=lambda item: item[0])
    print(f"Highest scorer: {profile['name']} (Roll: {profile['roll_number']})")
    print(f"Average marks: {average:.2f}")


def list_by_department():
    department = read_nonempty("Enter department: ").casefold()
    found = [p for p in students.values() if p["department"].casefold() == department]
    if not found:
        print("No students found in that department.")
        return
    for profile in found:
        print(f"{profile['roll_number']} - {profile['name']} ({profile['department']})")


def count_students():
    print(f"Total number of students: {len(students)}")
    print(f"Departments recorded: {', '.join(sorted(departments)) or 'None'}")
    print(f"Subjects recorded: {', '.join(sorted(subjects_catalog)) or 'None'}")
    print(f"Student clubs recorded: {', '.join(sorted(student_clubs)) or 'None'}")


def generate_report():
    print("\n--- Academic Report ---")
    count_students()
    calculate_average()
    highest_scorer()
    if students:
        print("\nStudents by department:")
        for department in sorted({p["department"] for p in students.values()}):
            names = [p["name"] for p in students.values()
                     if p["department"].casefold() == department.casefold()]
            print(f"{department}: {', '.join(names)}")


def show_menu():
    print("""
========== STUDENT MANAGEMENT SYSTEM ==========
1. Add student
2. Search student by roll number
3. Update student
4. Delete student
5. Display all students
6. Calculate overall average marks
7. Find highest scorer
8. List students by department
9. Count students and show collections
10. Generate academic report
0. Exit
""")


def main():
    while True:
        show_menu()
        choice = input("Choose an option: ").strip()
        actions = {
            "1": add_student,
            "2": search_student,
            "3": update_student,
            "4": delete_student,
            "5": display_all_students,
            "6": calculate_average,
            "7": highest_scorer,
            "8": list_by_department,
            "9": count_students,
            "10": generate_report,
        }
        if choice == "0":
            print("Thank you for using the Student Management System.")
            break
        action = actions.get(choice)
        if action:
            action()
        else:
            print("Invalid choice. Please select a menu option from 0 to 10.")


if __name__ == "__main__":
    main()
