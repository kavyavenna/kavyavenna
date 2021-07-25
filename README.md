include <fstream>
#include <iostream>
#include <memory>
#include <vector>
using namespace std;

//Note: Do not change any part of the existing code.
int main(int argc, char *argv[]) {
    std::vector<int> numVec;
    int nextNum;
    ifstream inFile;
    inFile.open(argv[1]);
    ofstream outfile;
    outfile.open("output");

    while(inFile >> nextNum){
       numVec.push_back(nextNum);
    }
    
    // Write your code to remove all occurences 3 contiguous numbers that add up to 0 from the vector numVec
    // Note that the output vector should not have any occurances where 3 contiguous numbers sum to 0

    std::vector<int> numVec2;
    int i=0;
    for(auto a:numVec)
    {
        numVec2.push_back(a);
        if(numVec2.size()>2)
        {
            int i=numVec2.size()-1;//index of last element
            if(numVec2[i]+numVec2[i-1]+numVec2[i-2]==0)
            {
                int x=3;
                while(x--)
                {
                    numVec2.pop_back();
                }
            }
        }
    }

   for(auto n:numVec2) {
      outfile << n << endl; 
   }
}
