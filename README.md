#include <iostream>
#include <cmath>
#include "diod.h"

using namespace std;

void LedDiod::setColor(string color)
{
    if (color == "green" || color == "Green")
    {
        green = color;
        showColor ();
    }
    else if (color == "red" || color == "Red")
    {
        red = color;
        showColor ();
    }
    else if (color == "blue" || color == "Blue")
    {
        blue = color;
        showColor ();
    }
    else
    {
        color = "red";
        red = color;
        bright = 0;
        showColor ();
    }
}

void LedDiod::showColor ()
{
    if(green == "green")
        cout << "led color is " << green << endl;
    else if (red == "red")
        cout << "led color is "<< red << endl;
    else if (blue == "blue")
        cout << "led color is " << blue << endl;
    else
        cout << "led color is " << red << endl;
}

void LedDiod::showBrightness()
{
    cout << "led brightness is " << bright << endl;
}

void LedDiod::setBrightness(int br)
{
    if(br > 0 and br <= 100)
    {
            bright=br;
            showBrightness();
    }
    else
        bright=0;
    
}

int LedDiod::calcDiodCurrent(double voltage)
{
    int n = 1;
    double Vt = 0.02585, Is=0.00001, I = 0;
    I=Is*(exp(voltage/(n*Vt))-1);
    return I;
