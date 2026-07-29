#include <stdio.h>
#include <string.h>

struct Hostel
{
    int id;
    char name[30];
    char room[10];
    char complaint[100];
    char status[20];
};

int main()
{
    struct Hostel s;
    int choice, action;

    while(1)
    {
        printf("\n====================================\n");
        printf(" HOSTEL COMPLAINT MANAGEMENT SYSTEM\n");
        printf("====================================\n");
        printf("1. Register Student\n");
        printf("2. Raise Complaint\n");
        printf("3. Warden Action\n");
        printf("4. View Complaint\n");
        printf("5. Exit\n");

        printf("\nEnter your choice: ");
        scanf("%d",&choice);

        switch(choice)
        {
            case 1:

                printf("\n--- Student Registration ---\n");

                printf("Enter Student ID: ");
                scanf("%d",&s.id);

                printf("Enter Student Name: ");
                scanf(" %[^\n]",s.name);

                printf("Enter Room Number: ");
                scanf("%s",s.room);

                printf("\nRegistration Successful!\n");
                break;

            case 2:

                printf("\n--- Raise Complaint ---\n");

                printf("Enter Complaint: ");
                scanf(" %[^\n]",s.complaint);

                strcpy(s.status,"Pending");

                printf("\nComplaint Submitted Successfully!\n");
                break;

            case 3:

                printf("\n--- Warden Action ---\n");
                printf("1. Approve Complaint\n");
                printf("2. Resolve Complaint\n");

                printf("Enter Choice: ");
                scanf("%d",&action);

                if(action==1)
                {
                    strcpy(s.status,"Approved");
                    printf("\nComplaint Approved!\n");
                }
                else if(action==2)
                {
                    strcpy(s.status,"Resolved");
                    printf("\nComplaint Resolved!\n");
                }
                else
                {
                    printf("\nInvalid Choice!\n");
                }

                break;

            case 4:

                printf("\n====== COMPLAINT DETAILS ======\n");
                printf("Student ID : %d\n",s.id);
                printf("Name       : %s\n",s.name);
                printf("Room No    : %s\n",s.room);
                printf("Complaint  : %s\n",s.complaint);
                printf("Status     : %s\n",s.status);
                printf("===============================\n");

                break;

            case 5:

                printf("\nThank You!\n");
                return 0;

            default:

                printf("\nInvalid Choice!\n");
        }
    }

    return 0;
}
