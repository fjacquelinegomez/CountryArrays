#include <iostream>
#include <fstream>
#include <string>

using namespace std;
const int rows = 10;
const int columns = 2;
// prototypes
void setValues(ifstream &, ifstream &, string [][columns], int[][columns], int);
void getMost(string [][columns], int [][columns], int);
void getLeast(string [][columns], int [][columns], int);
void both(string [][columns], int [][columns], int);

int main()
{
    string countries[10][2];
    int fruitProduced [10][2];
    ifstream oranges, apples;
    oranges.open("oranges.txt");
    apples.open("apples.txt");
    if (!oranges || !apples){
        cout << "File did not open. End of program.";
    } else {
        setValues(oranges, apples, countries, fruitProduced, rows);
        getMost(countries, fruitProduced, rows);
        getLeast(countries, fruitProduced, rows);
        both(countries, fruitProduced, rows);
    }

    return 0;
}

void setValues(ifstream& oranges, ifstream& apples, string countries[rows][columns], int fruitProduced[rows][columns], int rows){
    while(!oranges.eof() && !apples.eof()){
        for (int row = 0; row < rows; row++){
            oranges >> countries[row][0] >> fruitProduced[row][0];
            apples >> countries[row][1] >> fruitProduced[row][1];
        }
    }
        apples.close();
        oranges.close();
} // end setValues

void getMost(string countries[][columns], int fruitProduced[][columns], int rows){
    int mostOranges = 0;
    int mostApples = 0;
    for (int row = 0; row < rows; row++){
        if(fruitProduced[row][0] > fruitProduced[mostOranges][0]) mostOranges = row;
        if(fruitProduced[row][1] > fruitProduced[mostApples][1]) mostApples = row;
    }
    cout << countries[mostOranges][0] << " produced the most tons of oranges in 2019 with " << fruitProduced[mostOranges][0] << "." << endl;
    cout << countries[mostApples][1] << " produced the most tons of apples in 2019 with " << fruitProduced[mostApples][1] << "." << endl << endl;
}// end getMost

void getLeast(string countries[][columns], int fruitProduced[][columns], int rows){
    int leastOranges = 0;
    int leastApples = 0;
    for(int row = 0; row < rows; row++){
        if(fruitProduced[row][0] < fruitProduced[leastOranges][0]) leastOranges = row;
    } cout << countries[leastOranges][0] << " produced the least tons of oranges in 2019 with " << fruitProduced[leastOranges][0] << "." << endl;
    for(int row = 0; row < rows; row++){
        if (fruitProduced[row][1] < fruitProduced[leastApples][1])leastApples = row;
    } cout << countries[leastApples][1] << " produced the least tons of apples in 2019 with " << fruitProduced[leastApples][1] << "." << endl << endl;
}// end getLeast

void both(string countries[][columns], int fruitProduced[][columns], int rows){
    cout << "The following countries are in the Top 10 in both orange and apple production: " << endl;
        for (int row = 0; row < rows; row++){
                for (int z = 0; z < rows; z++){
                if(countries[row][0] == countries[z][1]){
                    cout << countries[row][0] << endl;
                }
            }
        }
} // end both
