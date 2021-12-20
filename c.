#include <stdio.h>
struct Employee
{
    char name[30], Com[30];
    int Id, salary;
} p, rp[30];

void read_Employee()
{
    FILE *read = fopen("Hello.txt", "r+");
    int count = 0;
    char c = getc(read);
    while (c!= EOF)
    {
        if (c == '\n')
            count++;
        c = getc(read);
    }
    rewind(read);
    int find = 0, id;
    printf("Enter the Id of Employee : ");
    scanf("%d", &id);
    int i = 0;
    for (; i < count; i++)
    {
        fscanf(read, "%s %d %d %s", rp[i].name, &rp[i].salary, &rp[i].Id, rp[i].Com);
        if (rp[i].Id == id)
        {
            find = i;
            break;
        }
    }
    if (i == count)
        printf("NO Employee FOUND");
    else
        printf("Name : %s\nSalary : %d\nEmployee Id : %d\nCompany Name : %s\n", rp[find].name, rp[find].salary, rp[find].Id, rp[find].Com);
    fclose(read);
}

void display_Employee()
{
    FILE *dataread = fopen("Hello.txt", "r");
    int count = 0;
    char c = getc(dataread);
    while (c != EOF)
    {
        if (c == '\n')
            count++;
        c = getc(dataread);
    }
    rewind(dataread);
    int temp = count;
    printf("\nSr.No.\tName\tSalary\tId\tCompany\n");
    while (count--)
    {
        fscanf(dataread, "%s %d %d %s", p.name, &p.salary, &p.Id, p.Com);
        printf("%d.\t%s\t%d\t%d\t%s\n", temp - count, p.name, p.salary, p.Id, p.Com);
    }
    fclose(dataread);
}

void delete_data()
{
    FILE *dataread = fopen("Hello.txt", "r");
    int count = 0;
    char c = getc(dataread);
    while (c != EOF)
    {
        if (c == '\n')
            count++;
        c = getc(dataread);
    }
    rewind(dataread);
    int id;
    printf("Enter the Id No. which is to be deleted : ");
    scanf("%d", &id);
    int i = 0;
    for (; i < count; i++)
    {
        fscanf(dataread, "%s %d %d %s", rp[i].name, &rp[i].salary, &rp[i].Id, rp[i].Com);
    }
    FILE *del = fopen("Hello.txt", "w");
    for (int i = 0; i < count; i++)
    {
        if (rp[i].Id == id)
            continue;
        fprintf(del, "%s %d %d %s", rp[i].name, rp[i].salary, rp[i].Id, rp[i].Com);
        fputc('\n', del);
    }
    fclose(dataread);
    fclose(del);
}

void write_data()
{
    FILE *datawrite = fopen("Hello.txt", "a");
    printf("Enter the Employee Name : ");
    scanf("%s", p.name);
    printf("Enter the Employee Salary : ");
    scanf("%d", &p.salary);
    printf("Enter the Employee Id : ");
    scanf("%d", &p.Id);
    printf("Enter The Employee Company : ");
    scanf("%s", p.Com);
    fprintf(datawrite, "%s %d %d %s", p.name, p.salary, p.Id, p.Com);
    fputc('\n', datawrite);
    fclose(datawrite);
}

int main()
{
    while (1)
    {
        int choice;
        printf("\n\n\tChoose a Option : \n1. Read the Employee Data\n2. Add a Employee data\n3. Delete a Employee data\n4. Display All Employees data\n5. Exit\n");
        scanf("%d", &choice);
        switch (choice)
        {
        case 1:
            read_Employee();
            break;
        case 2:
            write_data();
            break;
        case 3:
            delete_data();
            break;
        case 4:
            display_Employee();
            break;
        case 5:
            return 1;
            break;
        default:
            printf("Invalid Option");
        }
    }

    return 0;
}
