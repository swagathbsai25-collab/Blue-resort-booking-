# Blue-resort-booking-
Blue Resort booking
#include <stdio.h>
#include <string.h>

struct Customer {
    char name[50];
    char phone[20];
    int roomType;
    int days;
    float totalCost;
    int isBooked;
};

struct Customer blueResortBooking = {"", "", 0, 0, 0.0, 0};

void bookRoom() {
    int type;
    float pricePerDay = 0.0;

   printf("\n--- Room Types and Pricing ---\n");
    printf("1. Standard Room: Rs. 1000 per day\n");
    printf("2. Deluxe Room: Rs. 2000 per day\n");
    printf("3. Suite Room: Rs. 3000 per day\n");
    printf("Enter room type (1, 2, or 3): ");
    scanf("%d", &type);

  if (type == 1) {
        pricePerDay = 1000.0;
    } else if (type == 2) {
        pricePerDay = 2000.0;
    } else if (type == 3) {
        pricePerDay = 3000.0;
    } else {
        printf("Invalid room type selection!\n");
        return;
    }

   printf("Enter your name: ");
    scanf("%s", blueResortBooking.name);
    printf("Enter your phone number: ");
    scanf("%s", blueResortBooking.phone);
    printf("Enter number of days to stay: ");
    scanf("%d", &blueResortBooking.days);

   blueResortBooking.roomType = type;
    blueResortBooking.totalCost = pricePerDay * blueResortBooking.days;
    blueResortBooking.isBooked = 1;

  printf("\nRoom booked successfully at Blue Resort!\n");
    printf("Total Cost: Rs. %.2f\n", blueResortBooking.totalCost);
}

void viewBooking() {
    if (blueResortBooking.isBooked) {
        printf("\n--- Booking Details for Blue Resort ---\n");
        printf("Customer Name: %s\n", blueResortBooking.name);
        printf("Phone Number: %s\n", blueResortBooking.phone);
        printf("Room Type: ");
        if (blueResortBooking.roomType == 1)
             printf("Standard\n");
        else if (blueResortBooking.roomType == 2) 
                     printf("Deluxe\n");
        else if (blueResortBooking.roomType == 3) 
                     printf("Suite\n");
        printf("Days Staying: %d\n", blueResortBooking.days);
        printf("Total Amount: Rs. %.2f\n", blueResortBooking.totalCost);
    } 
else
      {
        printf("\nNo booking found.\n");
       }
}

int main() {
    int choice;

   while (1) {
        printf("\n===== Blue Resort Booking System =====\n");
        printf("1. Book a Room\n");
        printf("2. View My Booking\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

  switch (choice) 
  {
            case 1:
                bookRoom();
                break;
            case 2:
                viewBooking();
                break;
            case 3:
                printf("Thank you for using Blue Resort Booking System!\n");
                return 0;
           default:
              printf("Invalid choice. Please try again.\n");
       }
   }

  return 0;
}
