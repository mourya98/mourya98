include <fstream>
#include <iostream>
#include <memory>
#include <vector>
using namespace std;

//Note: Do not change any part of the existing code.
int main(int argc, char *argv[]) {
    std::vector<int> numVec;
    int NextNum;
    ifstream inFile;
    inFile.open(argv[1]);
    ofstream outfile;
    outfile.open("output");

    while(inFile >> NextNum){
       numVec.push_back(NextNum);
    }
    
    // Write your code to remove all occurences 3 contiguous numbers that add up to 0 from the vector numVec
    // Note that the output vector should not have any occurances where 3 contiguous numbers sum to 0

    std::vector<int> NumVec2;
    int i=0;
    for(auto a:NumVec)
    {
        NumVec2.push_back(a);
        if(NumVec2.size()>2)
        {
            int i=NumVec2.size()-1;//index of last element
            if(NumVec2[i]+NumVec2[i-1]+NumVec2[i-2]==0)
            {
                int x=3;
                while(x--)
                {
                    NumVec2.pop_back();
                }
            }
        }
    }

   for(auto n:NumVec2) {
      outfile << n << endl; 
   }
}
