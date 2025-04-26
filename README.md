# Module-7-Lab-Assignment

Name:Pranav Krishna T

Reg No:212224040241

EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include <stdio.h>

#define SIZE 5

struct Person {
    char name[50];
    int age;
};

int main() {
    struct Person people[SIZE];
    int i;

    // Input details
    printf("Enter details of %d people:\n", SIZE);
    for (i = 0; i < SIZE; i++) {
        printf("\nPerson %d:\n", i + 1);
        printf("Name: ");
        scanf(" %[^\n]", people[i].name);
        printf("Age: ");
        scanf("%d", &people[i].age);
    }

    printf("\nVaccine Eligibility:\n");
    for (i = 0; i < SIZE; i++) {
        printf("%s (Age %d): ", people[i].name, people[i].age);
        if (people[i].age >= 18) {
            printf("Eligible\n");
        } else {
            printf("Not Eligible\n");
        }
    }

    return 0;
}

```


Output:

![exp7](https://github.com/user-attachments/assets/bcda3830-6179-4319-83de-8c119dbaeaa0)


Result:
Thus, the program is verified successfully. 


EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION

Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:

```
#include <stdio.h>
#include <string.h>

// Define a structure
struct Student {
    char name[50];
    int marks1, marks2, marks3;
    float average;
};

// Function to calculate average (structure passed and returned)
struct Student calculateAverage(struct Student s) {
    s.average = (s.marks1 + s.marks2 + s.marks3) / 3.0;
    return s;
}

// Function to display student info (structure passed)
void displayStudent(struct Student s) {
    printf("\nStudent Details:\n");
    printf("Name   : %s\n", s.name);
    printf("Marks  : %d, %d, %d\n", s.marks1, s.marks2, s.marks3);
    printf("Average: %.2f\n", s.average);
}

int main() {
    struct Student s1;

    // Input student data
    printf("Enter student name: ");
    scanf(" %[^\n]", s1.name);
    printf("Enter 3 subject marks: ");
    scanf("%d %d %d", &s1.marks1, &s1.marks2, &s1.marks3);

    // Call function to compute average (returns structure)
    s1 = calculateAverage(s1);

    // Call function to display result
    displayStudent(s1);

    return 0;
}



```



Output:


![image](https://github.com/user-attachments/assets/3aeb4eee-a719-477f-9151-14f34cc65c8b)




Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

```
#include <stdio.h>
int main(){
    FILE *file;
    char filename[50];
    scanf("%s",filename);
    file=fopen(filename,"w");
    printf("%s File Created Successfully\n",filename);
    printf("%s File Opened\n",filename);
    fclose(file);
    printf("%s File Closed",filename);
}


```



Output:
![image](https://github.com/user-attachments/assets/6bba346f-9149-44c5-943e-514c03d1ec3b)




Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE

Aim:
To write a C program to read, a file and insert text in that file

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

```
#include <stdio.h>

int main() {
    char filename[100];
    char text[500];
    FILE *fp;

    // Get file name from user
    printf("Enter the file name: ");
    scanf("%s", filename);

    // Open file for writing ("w" mode clears existing content)
    fp = fopen(filename, "w");

    if (fp == NULL) {
        printf("Error opening the file.\n");
        return 1;
    }

    // Clear input buffer before using fgets
    getchar();

    // Get text from user
    printf("Enter the text to write in the file:\n");
    fgets(text, sizeof(text), stdin);

    // Write text into the file
    fputs(text, fp);

    // Close file
    fclose(fp);
    printf("Text written successfully to '%s'.\n", filename);

    return 0;
}

```



Output:



![image](https://github.com/user-attachments/assets/63c2bcc5-40fb-4f81-ad8d-c44dce8a021f)





Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:

```
#include <stdio.h>

// Define structure for student
struct Student {
    int rollNo;
    char name[50];
    float marks;
};

int main() {
    struct Student s;

    // Input student details
    printf("Enter student roll number: ");
    scanf("%d", &s.rollNo);

    printf("Enter student name: ");
    scanf(" %[^\n]", s.name); // Read string with spaces

    printf("Enter student marks: ");
    scanf("%f", &s.marks);

    // Display student details
    printf("\n--- Student Details ---\n");
    printf("Roll Number : %d\n", s.rollNo);
    printf("Name        : %s\n", s.name);
    printf("Marks       : %.2f\n", s.marks);

    return 0;
}

```



Output:

![image](https://github.com/user-attachments/assets/3d8425c8-991b-4492-be12-22888c27ce05)


Result:
Thus, the program is verified successfully


