# Hangman
Hangman Game in C++
#include <iostream>
#include <string>
#include <stdlib.h>
#include <ctime>
using namespace std;
int main()
{

	char choies;
	int win = 0, lose = 0, count = 0;
	cout << "$$$$$$$$$$ WELL COME TO THE HANGMAN GAME $$$$$$$$$$" << endl;
	cout << endl;
	cout << "You have to types only letter in one try" << endl;
	cout << endl;
	cout << "You have 5 tries to try and guess the Word" << endl;
	cout << endl;
	cout << "Now" << endl;
	cout << endl;
	cout << "Guess the word" << endl;
	do
	{

		int max_tries = 5;
		char letter;
		int wrong_guess = 0;
		string word;
		int guess = 0;

		const string wordlist[12] = { "buzzbombs",
			"squizzing",
			"whizzbang",
			"buzzkills",
			"jazziness",
			"showbizzy",
			"whizzkids",
			"bemuzzled",
			"blackjack",
			"buckjumps",
			"chazzanim",
			"chazzenim" };
		/*for (int i = 0; i<20; i++)
		{
		cout << words[i] << "  ";
		}*/
		srand(time(0));   //changing word every time because of #include <ctime> library
		word = wordlist[rand() % 12];
		cout << "* * * * * * * * *" << endl;
		//cout << word <<endl;
		while (wrong_guess < max_tries)
		{
			cin >> letter;
			//if (letter[1] == )

			string str = word;

			str.find(letter);
			if (str.find(letter)<10)
			{
				cout << "Got it " << letter << endl << endl;
				cout << "Enter another one " << endl;
				guess++;
				if (guess == 9)
				{
					cout << "Letters are correct" << endl;
					cout << "Word is " << word << endl;
					win++;

					break;
				}

			}
			else if (str.find(letter)>10)
			{
				cout << "Wrong Letter" << endl << endl;
				cout << "Please enter correct Letter" << endl;
				wrong_guess++;
				if (wrong_guess == 5)
				{
					cout << "Letters are not correct" << endl;
					cout << "Word is " << word << endl;
					lose++;
				}


			}
		}

		cout << "Did you want to play again (Press Y for yes) (Press N for No)" << endl;
		cin >> choies;


	} while (choies == 'y');
	cout << "Loses = " << lose << endl;
	cout << "Wins = " << win << endl;
	system("pause");
	return 0;
}
