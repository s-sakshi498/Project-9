# Project-9
Salary  management 
#include <stdio.h>

int main() {
    float salary[100];
    float *ptr = salary;   // pointer to array
    int n, i;
    float total = 0, highest, lowest;

    printf("Enter number of employees: ");
    scanf("%d", &n);

    printf("\nEnter salaries:\n");
    for (i = 0; i < n; i++) {
        printf("Employee %d: ", i + 1);
        scanf("%f", (ptr + i));   // pointer input
        total += *(ptr + i);
    }

    highest = lowest = *ptr;

    for (i = 1; i < n; i++) {
        if (*(ptr + i) > highest)
            highest = *(ptr + i);

        if (*(ptr + i) < lowest)
            lowest = *(ptr + i);
    }

    printf("\n--- Salary Report ---\n");
    printf("Total Salary: %.2f\n", total);
    printf("Average Salary: %.2f\n", total / n);
    printf("Highest Salary: %.2f\n", highest);
    printf("Lowest Salary: %.2f\n", lowest);

    printf("\n--- Salary List ---\n");
    for (i = 0; i < n; i++) {
        printf("Employee %d: %.2f\n", i + 1, *(ptr + i));
    }

    return 0;
}
