# 🎓 Student Management System

---

## 📚 Course Information
Course: (طرق البرمجة المتقدمة)  
Instructor: (رزان فيصل الفقير)

---

## 👩‍💻 Project Description
This project is a Student Management System developed using Python.  
It helps manage student records using Object-Oriented Programming and File Handling.

The system allows:
- Adding new students  
- Viewing all students  
- Updating student information  
- Deleting students  
- Saving data to a file  
- Loading data automatically when the program starts  

---

## 👩‍🏫 Team Members
- Fatima Abdullah  
- Norah Saad  
- Raghad Abdulrahman  
- Juana Mesfer  
- Nasayim Salem  
- Amjad alhailm 

---

## 🧩 Concepts Used
- Object-Oriented Programming (OOP)  
- Classes & Objects  
- Inheritance  
- Encapsulation  
- File Handling  
- Input Validation  
- Menu-driven system  

---

## 📁 Project Files
- main.py → Python source code  
- students_data.txt → Stores student data  

---

## ▶️ How to Run the Program
1. Open the project in Python (Jupyter / Anaconda / VS Code)  
2. Run the file `main.py`  
3. Use the menu options to interact with the system  

---

## 📌 Note
All program examples and output are implemented and can be tested directly in the Python file (main.py).

---

## 👩‍💻 Code Contribution & Detailed Explanation

### 🔹 Fatima Abdullah (Parent Class & Encapsulation)
```python
class Person:
    def __init__(self, name, person_id):
        self.name = name
        self.__id = person_id

    def get_id(self):
        return self.__id
Explanation:
Fatima implemented the parent class Person, which represents the base structure for any individual in the system.
The class includes two main attributes: name and person_id. The person_id is defined as a private attribute using double underscores (__id), which demonstrates the concept of encapsulation in Object-Oriented Programming.

Encapsulation is used here to restrict direct access to sensitive data. Instead of accessing the ID directly, a getter method get_id() is provided. This ensures controlled access and protects the integrity of the data.

This design improves security and follows best practices in OOP by separating internal data representation from external access.


🔹 NORAH SAAAD (INHIRTANCE)


class Student(Person):
    def __init__(self, name, person_id, grade):
        super().__init__(name, person_id)
        self.grade = grade

    def display(self):
        print("Name:", self.name, "| ID:", self.get_id(), "| Grade:", self.grade)
Explanation:
Nora implemented the Student class, which inherits from the Person class. This demonstrates the concept of inheritance, where a child class reuses the properties and methods of a parent class.

The Student class extends the functionality of Person by adding a new attribute called grade, which represents the student’s score. The super() function is used to call the constructor of the parent class and initialize inherited attributes.

Additionally, the display() method is responsible for presenting the student’s data in a readable format. This improves user interaction and makes the output more organized.

This part of the code clearly shows how inheritance reduces code duplication and improves structure.



🔹 Raghad Abdulrahman & Juana Mesfer (File Handling)

def load_students():
    students = []
    if os.path.exists("students_data.txt"):
        file = open("students_data.txt", "r")
        for line in file:
            data = line.strip().split(",")
            if len(data) == 3:
                students.append(Student(data[0], data[1], int(data[2])))
        file.close()
    return students
def save_students(students):
    file = open("students_data.txt", "w")
    for s in students:
        file.write(s.name + "," + s.get_id() + "," + str(s.grade) + "\n")
    file.close()

Explanation:
Raghad and Juana handled the file management operations, which are essential for data persistence.

The load_students() function reads student data from the file students_data.txt. Each line in the file is processed by removing extra spaces and splitting the values using commas. The extracted values (name, ID, and grade) are then used to create Student objects, which are stored in a list. This allows the program to restore previously saved data when it starts.

The save_students() function is responsible for writing updated data back into the file. It loops through the student list and stores each student’s information in a structured format.

Together, these functions ensure that all operations (add, update, delete) are preserved even after the program is closed. This fulfills the requirement of file handling and demonstrates how programs interact with external storage.



🔹 Nasayim Salem & Amjad (Main Program Logic)

def main():
    students_list = load_students()

    while True:
        print("\n--- Student System ---")
        print("1- Add Student")
        print("2- Show Students")
        print("3- Update Student")
        print("4- Delete Student")
        print("5- Save & Exit")

        choice = input("Choose: ")

Explanation:
Nasayim and Amjad implemented the main logic of the program, which controls the overall flow of execution.

At the beginning, the program loads all student data using the load_students() function. Then, a continuous loop (while True) is used to display a menu that allows the user to interact with the system.

Each option in the menu corresponds to a specific operation such as adding, viewing, updating, or deleting students. The program uses conditional statements (if/elif) to determine which operation to perform based on user input.

This part also includes input validation to ensure that incorrect data (such as non-numeric grades) is not accepted.

Overall, this section integrates all components of the system and provides a simple and user-friendly interface for managing student data.
