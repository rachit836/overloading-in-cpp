

---

# **OVERLOADING IN CPP**

**Demonstration of Function, Constructor, and Operator Overloading in C++**

---

## **Aim**

To study and implement **function overloading**, **constructor overloading**, and **operator overloading** concepts in C++ with practical examples.

---

## **Question 1: Constructor Overloading 1**

### **Theory**

Constructor overloading allows a class to have more than one constructor with different parameter lists. This enables creating objects in multiple ways.
For example, a default constructor initializes with fixed values, and a parameterized constructor initializes with user-defined values.

### **Logic Code**

```cpp
#include <iostream>
using namespace std;

class Student {
    string name;
    int age;
public:
    Student() {
        name = "Unknown";
        age = 0;
    }
    Student(string n, int a) {
        name = n;
        age = a;
    }
    void display() {
        cout << "Name: " << name << ", Age: " << age << endl;
    }
};

int main() {
    Student s1;              // Default constructor
    Student s2("Rachit", 20); // Parameterized constructor
    s1.display();
    s2.display();
    return 0;
}
```

### **Example Output**

```
Name: Unknown, Age: 0
Name: Rachit, Age: 20
```

---

## **Question 2: Constructor Overloading 2**

### **Theory**

Constructor overloading can also handle more complex initializations. By defining multiple constructors, you can set up an object with varying levels of data.

### **Logic Code**

```cpp
#include <iostream>
using namespace std;

class Rectangle {
    int length, breadth;
public:
    Rectangle() {
        length = 0; breadth = 0;
    }
    Rectangle(int l, int b) {
        length = l; breadth = b;
    }
    int area() {
        return length * breadth;
    }
};

int main() {
    Rectangle r1;
    Rectangle r2(10, 5);
    cout << "Area 1: " << r1.area() << endl;
    cout << "Area 2: " << r2.area() << endl;
    return 0;
}
```

### **Example Output**

```
Area 1: 0
Area 2: 50
```

---

## **Question 3: Function Overloading**

### **Theory**

Function overloading allows multiple functions with the same name but different parameter lists.
It helps in performing similar operations with different data types or number of arguments.

### **Logic Code**

```cpp
#include <iostream>
using namespace std;

int add(int a, int b) {
    return a + b;
}
double add(double a, double b) {
    return a + b;
}
int add(int a, int b, int c) {
    return a + b + c;
}

int main() {
    cout << "Sum 2 int: " << add(3, 4) << endl;
    cout << "Sum 2 double: " << add(2.5, 3.7) << endl;
    cout << "Sum 3 int: " << add(1, 2, 3) << endl;
    return 0;
}
```

### **Example Output**

```
Sum 2 int: 7
Sum 2 double: 6.2
Sum 3 int: 6
```

---

## **Question 4: Operator Overloading – Calculator**

### **Theory**

Operator overloading lets you redefine how operators (+, -, \*, /) behave for user-defined types.
Here, we overload operators to perform calculator-style operations on objects.

### **Logic Code**

```cpp
#include <iostream>
using namespace std;

class Calculator {
    int value;
public:
    Calculator(int v=0) {
        value = v;
    }
    Calculator operator+(Calculator c) {
        return Calculator(value + c.value);
    }
    Calculator operator-(Calculator c) {
        return Calculator(value - c.value);
    }
    void display() {
        cout << "Value: " << value << endl;
    }
};

int main() {
    Calculator c1(20), c2(10);
    Calculator c3 = c1 + c2;
    Calculator c4 = c1 - c2;
    c3.display();
    c4.display();
    return 0;
}
```

### **Example Output**

```
Value: 30
Value: 10
```

---

## **Question 5: Operator Overloading – Complex Numbers**

### **Theory**

Complex numbers can be added/subtracted by overloading operators to handle real and imaginary parts separately.

### **Logic Code**

```cpp
#include <iostream>
using namespace std;

class Complex {
    int real, imag;
public:
    Complex(int r=0, int i=0) {
        real = r; imag = i;
    }
    Complex operator+(Complex c) {
        return Complex(real + c.real, imag + c.imag);
    }
    void display() {
        cout << real << " + " << imag << "i" << endl;
    }
};

int main() {
    Complex c1(3,4), c2(1,2);
    Complex c3 = c1 + c2;
    c3.display();
    return 0;
}
```

### **Example Output**

```
4 + 6i
```

---

## **Conclusion**

Through this experiment, we learned:

* **Function Overloading** allows multiple functions with the same name but different parameters.
* **Constructor Overloading** allows initializing objects in various ways.
* **Operator Overloading** enables using standard operators with user-defined types.

These features make C++ a powerful **object-oriented programming language**, providing flexibility, code reusability, and readability in real-world applications.

---


