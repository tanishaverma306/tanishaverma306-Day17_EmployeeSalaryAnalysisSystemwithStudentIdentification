#include <stdio.h>
Includes the standard input/output library — needed for functions like printf() and scanf().

int main() {
The starting point of the program. Every C program begins execution from the main() function.

int employees, Salary[10];
char Sec;
char name[100];
char Rno[20];
Declares variables:
employees – to store number of employees.
Salary[10] – an array to store up to 10 employee salaries.
Sec – to store a single character for section.
name[100] – to store your name (up to 99 characters).
Rno[20] – to store your registration number (like AP123456789).

printf("Enter your Name: ");
scanf("%99s", name);
Asks the user for their name and stores it in the variable name.

printf("Enter your Registration number: ");
scanf("%19s", Rno);
Takes the registration number as a string (since it contains both letters and numbers).

printf("Enter your Section: ");
scanf(" %c", &Sec);
Takes a single character input for section.
(Notice the space before %c — it ignores any leftover newline character from previous inputs.)

printf("Enter number of employees:\n");
scanf("%d", &employees);
Asks for how many employees there are and stores that number in employees.

for(int i = 0; i < employees; i++) {
printf("Enter the salaries \n");
scanf("%d", &Salary[i]);
printf("Salary of employee %d is %d\n", i+1, Salary[i]);
}
A for loop that runs once for each employee:
Takes each employee’s salary as input.
Prints it back to confirm.

printf("======Menu======\n");
printf("1. Display All salaries\n");
printf("2.Display Total and Average Salary\n");
printf("3. Display Highest and Lowest Salary\n");
printf("4. Count Above/Below Average\n");
printf("5. Display Sortes Salaries\n");
printf("6. Exit\n");
printf("Enter your choice: ");
Displays a menu of choices for the user to select what they want to do with the salary data.

int choice;
scanf("%d", &choice);
Takes the user’s choice as an integer.

if (choice==1) {
printf("All salaries are:\n");
for(int i=0; i<employees; i++) {
printf("Salary of employee %d is %d\n", i+1, Salary[i]);
}
}
Choice 1: Displays all entered salaries one by one.

else if (choice==2) {
int total=0;
for(int i=0; i<employees; i++) {
total += Salary[i];
}
float average = (float)total / employees;
printf("Total Salary: %d\n", total);
printf("Average Salary: %f\n", average);
}
Choice 2:
Adds all salaries to find the total.
Calculates average = total ÷ number of employees.
Displays both total and average.

else if (choice==3) {
int highest = Salary[0];
int lowest = Salary[0];
for(int i=1; i<employees; i++) {
if(Salary[i] > highest) {
highest = Salary[i];
}
if(Salary[i] < lowest) {
lowest = Salary[i];
}
}
printf("Highest Salary: %d\n", highest);
printf("Lowest Salary: %d\n", lowest);
}
Choice 3:
Finds and prints the highest and lowest salaries by comparing all values in the array.

else if (choice==4) {
int total=0;
for(int i=0; i<employees; i++) {
total += Salary[i];
}
float average = (float)total / employees;
int above=0, below=0;
for(int i=0; i<employees; i++) {
if(Salary[i] > average) {
above++;
} else {
below++;
}
}
printf("Number of employees above average: %d\n", above);
printf("Number of employees below average: %d\n", below);
}
Choice 4:
Recalculates the average.
Counts how many employees earn above and below the average salary.

else if (choice==5) {
for(int i=0; i<employees-1; i++) {
for(int j=0; j<employees-i-1; j++) {
if(Salary[j] > Salary[j+1]) {
int temp = Salary[j];
Salary[j] = Salary[j+1];
Salary[j+1] = temp;
}
}
}
printf("Sorted Salaries:\n");
for(int i=0; i<employees; i++) {
printf("Salary of employee %d is %d\n", i+1, Salary[i]);
}
}
Choice 5:
Sorts all salaries in ascending order using the Bubble Sort algorithm.
Prints the sorted list.

else if (choice==6) {
printf("Exiting the program.\n");
}
Choice 6: Ends the program.

else {
printf("Invalid choice. Please try again.\n");
}
If the user enters a number not between 1–6, this message appears.

return 0;
}
Ends the program successfully.
