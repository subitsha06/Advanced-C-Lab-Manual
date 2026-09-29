# NAME:K SUBITSHA 
# REG NO:212225060278
## EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

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


struct eligible {
    int age;
    char n[50]; 
};

int main() {
    int i, nPersons;

    
    printf("Enter the number of persons: ");
    scanf("%d", &nPersons);

    
    struct eligible e[nPersons];

   
    for(i = 0; i < nPersons; i++) {
        printf("\nEnter name of person %d: ", i + 1);
        scanf(" %[^\n]", e[i].n);  
        printf("Enter age of %s: ", e[i].n);
        scanf("%d", &e[i].age);
    }

    
    printf("\nVaccine Eligibility Details:\n");
    for(i = 0; i < nPersons; i++) {
        if(e[i].age <= 6)
            printf("%s (Age %d) - Vaccine Eligibility: No\n", e[i].n, e[i].age);
        else
            printf("%s (Age %d) - Vaccine Eligibility: Yes\n", e[i].n, e[i].age);
    }

    return 0;
}
```
Output:


<img width="500" height="405" alt="image" src="https://github.com/user-attachments/assets/e068565f-3a12-433d-80ec-59a712404268" />

Result:
Thus, the program is verified successfully. 


## EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
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

struct numbers {
    int a;
    int b;
};

struct numbers add(struct numbers n) {
    struct numbers result;
    result.a = n.a + n.b;
    result.b = 0;
    return result;
}

int main() {
    struct numbers n, sum;
    printf("Enter value for a: ");
    scanf("%d", &n.a);
    printf("Enter value for b: ");
    scanf("%d", &n.b);

    sum = add(n);
    printf("Sum of %d and %d is %d\n", n.a, n.b, sum.a);

    return 0;
}
```

Output:

<img width="413" height="211" alt="image" src="https://github.com/user-attachments/assets/d9a742db-655e-45c3-b8b6-c7b7ba344074" />

Result:
Thus, the program is verified successfully


## EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

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
#include <stdlib.h>

int main() {
    FILE *p;
    char name[100];
    printf("Enter the file name: ");
    scanf("%s", name);
    printf("File %s will be created successfully.\n", name);
    p = fopen(name, "w");
    if (p == NULL) {
        printf("Error in opening the file.\n");
        return 1;
    }
    printf("File %s opened successfully.\n", name);
    fclose(p);
    printf("File %s closed successfully.\n", name);
    return 0;
}
```
Output:

<img width="466" height="216" alt="image" src="https://github.com/user-attachments/assets/a0cbec75-3bc7-42ea-9930-7396693020dd" />

Result:
Thus, the program is verified successfully
 
## EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
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
#include <stdlib.h>

int main() {
    FILE *p;
    char name[100], text[100];
    int num, i;
    printf("Enter the file name: ");
    scanf("%s", name);
    printf("Enter the number of strings: ");
    scanf("%d", &num);
    p = fopen(name, "w");
    if (p == NULL) {
        printf("Error in opening the file.\n");
        return 1;
    }
    printf("File %s opened successfully.\n", name);
    for(i = 0; i < num; i++) {
        printf("Enter string %d: ", i + 1);
        scanf(" %[^\n]", text);
        fputs(text, p);
        fputs("\n", p);
    }
    fclose(p);
    printf("Data added successfully to %s.\n", name);
    return 0;
}
```

Output:

<img width="395" height="217" alt="image" src="https://github.com/user-attachments/assets/60ede6a8-e2f5-4dbe-82f4-fd1789c10c0c" />

Result:
Thus, the program is verified successfully

## Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

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

#include <stdio.h>
#include <stdlib.h>

struct subject {
    char name[50];
    int marks;
};

int main() {
    int n, i;
    struct subject *s;

    printf("Enter the number of subjects: ");
    scanf("%d", &n);

    s = (struct subject*)malloc(n * sizeof(struct subject));
    if(s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    for(i = 0; i < n; i++) {
        printf("Enter name of subject %d: ", i + 1);
        scanf(" %[^\n]", s[i].name);
        printf("Enter marks of %s: ", s[i].name);
        scanf("%d", &s[i].marks);
    }

    printf("\nSubject Details:\n");
    for(i = 0; i < n; i++) {
        printf("Subject: %s, Marks: %d\n", s[i].name, s[i].marks);
    }

    free(s);
    return 0;
}


Output:

<img width="496" height="398" alt="image" src="https://github.com/user-attachments/assets/c172c6fd-6802-4a49-837b-93c9dd627508" />


Result:
Thus, the program is verified successfully
