# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    float length, width, area;
    float *ptrLength, *ptrWidth;
    ptrLength = &length;
    ptrWidth = &width;
    scanf("%f", ptrLength);
    scanf("%f", ptrWidth);
    area = (*ptrLength) * (*ptrWidth);
    printf("Area of rectangle = %f sq. units\n", area);

    return 0;
}
```
## OUTPUT
![image](https://github.com/user-attachments/assets/4cb515c8-9302-4eb1-ab22-dc7723ca8290)

## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'C PROGRAM' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    char *str = (char *)malloc(11 * sizeof(char)); 

    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1; 
    }
    str[0] = 'C';
    str[1] = ' ';
    str[2] = 'P';
    str[3] = 'R';
    str[4] = 'O';
    str[5] = 'G';
    str[6] = 'R';
    str[7] = 'A';
    str[8] = 'M';
    str[9] = '\0';

    printf("%s\n", str);

    free(str);

    return 0;
}
```
## OUTPUT
![image](https://github.com/user-attachments/assets/529be820-9ee4-4607-bf27-0abd2b5813fe)

## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully

# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct Student {
    char name[50];
    int roll_number;
    float marks;
};

int main() {
    struct Student student;

    fgets(student.name, sizeof(student.name), stdin);
    scanf("%d", &student.roll_number);
    scanf("%f", &student.marks);
    printf("Displaying Information:\n");
    printf("Name: %s", student.name);
    printf("Roll number: %d\n", student.roll_number);
    printf("Marks: %.1f\n", student.marks);

    return 0;
}
```
## OUTPUT
![image](https://github.com/user-attachments/assets/2a85f264-4c06-4cf0-be89-e37537dc677b)


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

C program to read and print an employee's detail using structure

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct Employee {
    char name[50];
    int id;
    float salary;
};

int main() {
    struct Employee emp;
    scanf(" %[^\n]", emp.name); 
    scanf("%d", &emp.id);   
    scanf("%f", &emp.salary);  

    printf("Entered detail is:\n");
    printf("Name: %s\n", emp.name);
    printf("Id: %d\n", emp.id);
    printf("Salary: %.2f\n", emp.salary);

    return 0;
}
```
 ## OUTPUT
![image](https://github.com/user-attachments/assets/954ece93-47ea-4e42-9ab7-6449f758a4b1)


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Salary using the concept of structure
 


# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Write a ‘C’ program to read(regno & 3 subjects marks) and store the details of a student and calculate the total and percentage using Nested Structures.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>

struct marks {
    int subject1;
    int subject2;
    int subject3;
};

struct student {
    int regno;
    struct marks m;
    float total;
    float percentage;
};

void calculate(struct student* s) {
    s->total = s->m.subject1 + s->m.subject2 + s->m.subject3;
    s->percentage = (s->total / 300.0) * 100;
}

int main() {
    struct student students[5];
    int i;
    for (i = 0; i < 5; i++) {
       
        scanf("%d", &students[i].regno);
        scanf("%d", &students[i].m.subject1);
        scanf("%d", &students[i].m.subject2);
        scanf("%d", &students[i].m.subject3);

        calculate(&students[i]);
    }

    printf("Student Details are\n");
    for (i = 0; i < 5; i++) {
        printf("%d       %d       %d       %d       %.2f       %.2f\n", 
            students[i].regno, 
            students[i].m.subject1, 
            students[i].m.subject2, 
            students[i].m.subject3, 
            students[i].total, 
            students[i].percentage);
    }

    return 0;
}
```
## OUTPUT
![image](https://github.com/user-attachments/assets/ed0dd373-8c3e-4a3c-9bb5-7082c9966c4b)

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


