# Module-7-Lab-Assignment
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

// Structure to hold person information
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

    // Check eligibility
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

