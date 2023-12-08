# Nishant-tewatia-project
#include <stdio.h>
#include <ctype.h>
int main()
{
char gender, choice = 'Y', vote;
char name[25];
int age;
int vote1 = 0, vote2 = 0, vote3 = 0;
while (choice == 'Y')
{
tryagain:
printf("Your gender is: Male (M) or Female (F): ");
scanf("%s", &gender);
gender = toupper(gender);
if (gender == 'M')
{
printf("Male");
}
else if (gender == 'F')
{
printf("Female");
}
else
{
printf("\nPlease enter valid gender.\n");
goto tryagain;
}
printf("\nEnter your name: ");
scanf(" %s", &name);
if (gender == 'M')
{
printf("You are Mister %s", name);
}
else if (gender == 'F')
{
printf("You are Miss %s", name);
}
else
{
printf("You are Mister/Miss %s", name);
}
printf("\nWhat is your age? ");
scanf("%d", &age);
jump:
if (age >= 18)
{
move:
printf("\nWho would you like to vote:\n\nA. BJP B. AAP C. Congress\tPlease select\n(A)
(B) (C) : ");
scanf(" %c", &vote);
vote = toupper(vote);
switch (vote)
{
case 'A':
vote1++;
break;
case 'B':
vote2++;
break;
case 'C':
vote3++;
break;
default:
printf("\nInvalid option, please choose a valid option.\n");
goto move;
break;
}
}
else if (age <= 0 || age > 150)
{
printf("\nError, please enter a valid age.\n");
printf("\nWhat is your age? ");
scanf(" %d", &age);
goto jump;
}
else
{
printf("\nSorry, you're not eligible to vote.\n");
}
printf("\nWould you like to vote again? Yes (Y) or No (N): ");
scanf(" %c", &choice);
choice = toupper(choice);
}
printf("\nVoting has been ended: BJP: %d, AAP: %d, Congress: %d\n", vote1, vote2, vote3);
if (vote1 > vote2 > vote3)
{
printf("BJP is the winner!");
}
else if (vote2 > vote1 > vote3)
{
printf("AAP is the winner!");
}
else if (vote3 > vote2 > vote1)
{
printf("Congress is the winner!");
}
else
{
printf("It's a tie!");
}
return 0;
  }
