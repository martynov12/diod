#include <iostream>
#include <cmath>

using namespace std;

class LedDiod
{
    private:
        int bright = 0; 
        string red, green, blue;
    public:
        void showColor();
        void setColor(string color);
        void setBrightness(int br);
        void showBrightness();
        int calcDiodCurrent(double voltage);
};
