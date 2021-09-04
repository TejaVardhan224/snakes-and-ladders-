#include<stdio.h>
#include<conio.h>
#include<time.h>
#include<stdlib.h>
int eval(int,int,char[]);
void main() {
	int player1=0,player2=0,counter,temp,game;
	char name1[10],name2[10],c;
	srand(time(NULL));
	while(1) {
	printf("\ndo u wanna play game enter 0 or 1 ");
	scanf("%d",&game);
	if(game != 0) {

	printf("\nname type cheii mawa broo.. ");
	scanf("%s",name1);
	printf("\nne name kuda type cheii mawa bro... "); 
	scanf("%s",name2);

	while(player1 < 50 && player2 < 50) {

        printf("\n  %s  Enter any character and press enter for die roll ",name1);
        getchar();
        scanf("%c",&c);
		counter = rand() % 6;
		printf("\ndie value = %d",counter); 
		temp = eval(player1,counter,name1);
			if(temp == 0) {
			    printf("nuvvu gelichav mawaa broo");
				player1=0;
				player2=0;
				break;
			}
			if(temp == -5555) {
			    temp = 0;
			}
		player1 = player1 +temp;
		printf("\nplayer1 value = %d",player1);
		printf("\nplayer2 value = %d",player2);


		printf("\n   %s   Enter any character and press enter for die roll \n",name2);
		getchar();
		scanf("%c",&c);
		counter = rand() % 6;
		printf("\ndie value = %d",counter);
		temp = eval(player2,counter,name2);
			if(temp == 0) {
			    printf("nuvuu gelichav mawaaa broo");
				player1=0;
				player2=0;
				break;
			}
		player2 = player2+temp;
		printf("\nplayer1 value = %d",player1);
		printf("\nplayer2 value = %d",player2);
	}
	}
	else{
	exit(0);
}
}
}
int eval(int playerval,int counter,char name[10]) {
	int temp,n=0;
	if(counter == 0) {
	    return 1;
	    exit(1);
	}
	temp = playerval +counter;
	if(temp == 50) {
		return 0;
		exit(1);
	}
	else if(temp >50) {
		printf("\nnokkadu mawa broo");
		return -5555;
		}
	else {
		switch(temp) {
			case 6:
			n = counter + 8;
			printf("neku ladder vachindi broo + 8 ");
			break;

			case 16:
			n =  counter - 12;
			printf("neku snake vachindi broo - 12 pedda snake eee idhi");
			break;
			
			case 17:
			n =  counter + 6;
			printf("neku ladder vachindi broo + 6 ");
			break;
			
			case 27:
			n =  counter + 6;
			printf("neku ladder vachindi broo + 6 ");
			break;

			case 29:
			n =  counter - 19;
			break;

			case 38:
			n =  counter + 5;
			printf("neku ladder vachindi broo + 5 ");
			break;

			case 39:
			n = counter - 19;
			break;

			case 45:
			n = counter - 11;
			break;
			
			default:
			n = counter;
		}
	}
	return n;
}
