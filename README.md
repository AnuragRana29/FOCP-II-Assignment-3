#include "Person.cpp"

class Student : public Person {
private:
    string enrollmentDate;
    string program;
    double gpa;

public:
    Student(string n, int a, string i, string c, string ed, string p, double g)
        : Person(n, a, i, c) {
        setEnrollmentDate(ed);
        setProgram(p);
        setGPA(g);
    }

    ~Student() {}

    string getEnrollmentDate() { return enrollmentDate; }
    void setEnrollmentDate(string ed) { enrollmentDate = ed; }

    string getProgram() { return program; }
    void setProgram(string p) { program = p; }

    double getGPA() { return gpa; }
    void setGPA(double g) {
        if (g >= 0.0 && g <= 4.0) gpa = g;
    }

    void displayDetails() override {
        Person::displayDetails();
        cout << "Enrollment Date: " << enrollmentDate << endl;
        cout << "Program: " << program << endl;
        cout << "GPA: " << gpa << endl;
    }

    double calculatePayment() override {
        return 20000.0;
    }
};# FOCP-II-Assignment-3
