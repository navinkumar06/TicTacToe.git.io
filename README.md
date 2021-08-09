# //TicTacToe.git.io
//  Project name is Tic-Tac-Toe game in C .

// The game is developed for full-time entertainment and enthusiasms.
//  Though the proposed game is an action game, it doesn’t   involve any violence.
// This game is very popular and is fairly simple by itself.
// It is actually a two player game.
// In this game, there is a board with n x n squares.
//  In our game, it is 3 x 3 squares.
//  The goal of Tic-Tac-Toe is to be one of the players to get three same symbols in a row - horizontally, vertically or  diagonally - s on a 3 x 3 grid .
 
 //   source  code
 
 
#include <stdio.h>
#include <conio.h>
#include <windows.h>

char square[10] = { 'o', '1', '2', '3', '4', '5', '6', '7', '8', '9' };

int checkwin();
void board(string,string);

int main()
{

    char name1[50];
    char name2[50];
    int player = 1, i, choice;
    SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE),BACKGROUND_BLUE|BACKGROUND_GREEN);
printf("\n\t We have added the background colour.......... ");
SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE),BACKGROUND_BLUE|BACKGROUND_GREEN|BACKGROUND_RED|BACKGROUND_INTENSITY);
printf("\n\n\tQUANTUM  UNIVERSITY ,ROORKEE         ");
    printf("\n\n\t       PROJECT          \n\n");

    SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE),BACKGROUND_BLUE|BACKGROUND_RED|BACKGROUND_INTENSITY);
printf("\n\n Enter First Gamer Name: ");
scanf("%s",name1);

SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE),BACKGROUND_BLUE|BACKGROUND_GREEN|BACKGROUND_INTENSITY);
printf("\n\n Enter Second  Gamer Name: ");
scanf("%s",name2);
    char mark;
    do
    {
        board(name1, name2);
        player = (player % 2) ? 1 : 2;
if(player==1){
        printf(" %s your turn, enter a number:  ", name1);
        scanf("%d", &choice);
}
else
{
    printf(" %s your turn, enter a number:  ", name2);
        scanf("%d", &choice);
}

  mark = (player == 1) ? 'X' : 'O';

        if (choice == 1 && square[1] == '1')
            square[1] = mark;

        else if (choice == 2 && square[2] == '2')
            square[2] = mark;

        else if (choice == 3 && square[3] == '3')
            square[3] = mark;

        else if (choice == 4 && square[4] == '4')
            square[4] = mark;

        else if (choice == 5 && square[5] == '5')
            square[5] = mark;

        else if (choice == 6 && square[6] == '6')
            square[6] = mark;

        else if (choice == 7 && square[7] == '7')
            square[7] = mark;

        else if (choice == 8 && square[8] == '8')
            square[8] = mark;

        else if (choice == 9 && square[9] == '9')
            square[9] = mark;

        else
        {
            printf("Invalid move Again  !!");

            player--;
            getch();
        }
        i = checkwin();

        player++;
    }while (i ==  - 1);

    board(name1,name2);

    if (i == 1)
        printf("==>\n\a\t  Congratulations  %s , you  won !! ",name1);
    else
        printf("==>\aGame draw");

    getch();

    return 0;
}

/*****

FUNCTION TO RETURN GAME STATUS
1 FOR GAME IS OVER WITH RESULT
-1 FOR GAME IS IN PROGRESS
O GAME IS OVER AND NO RESULT
 ******/

int checkwin()
{
    if (square[1] == square[2] && square[2] == square[3])
        return 1;

    else if (square[4] == square[5] && square[5] == square[6])
        return 1;

    else if (square[7] == square[8] && square[8] == square[9])
        return 1;

    else if (square[1] == square[4] && square[4] == square[7])
        return 1;

    else if (square[2] == square[5] && square[5] == square[8])
        return 1;

    else if (square[3] == square[6] && square[6] == square[9])
        return 1;

    else if (square[1] == square[5] && square[5] == square[9])
        return 1;

    else if (square[3] == square[5] && square[5] == square[7])
        return 1;

    else if (square[1] != '1' && square[2] != '2' && square[3] != '3' &&
        square[4] != '4' && square[5] != '5' && square[6] != '6' && square[7]
        != '7' && square[8] != '8' && square[9] != '9')

        return 0;
    else
        return  - 1;
}


/*********
FUNCTION TO DRAW BOARD OF TIC TAC TOE WITH PLAYERS MARK
 ********/


void board(name1,name2)
{
    system("cls");
    printf("\n\t        Tic Tac Toe\n\n");

    printf("\n\n\tQUANTUM  UNIVERSITY ,ROORKEE");
    printf("\n\n\t    END SEMESTER  EXAM\n\n");
    printf("\n\tDeveloped  by  -  NAVIN KUMAR....    \n\n");

    printf("\t   %s - (X)  &  %s  - (O)\n\n\n",name1,name2);

    printf("\t------------------\n");
    printf("\t     |     |     \n");
    printf("\t  %c  |  %c  |  %c \n", square[1], square[2], square[3]);

    printf("\t_____|_____|_____\n");
    printf("\t     |     |     \n");

    printf("\t  %c  |  %c  |  %c \n", square[4], square[5], square[6]);

    printf("\t_____|_____|_____\n");
    printf("\t     |     |     \n");

    printf("\t  %c  |  %c  |  %c \n", square[7], square[8], square[9]);

    printf("\t-------------------\n\n\n\n");
}

/*********
END OF PROJECT
 ********/






