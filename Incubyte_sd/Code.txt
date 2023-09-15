#include <bits/stdc++.h>
using namespace std;

class ChandraYaan3
{
private:
    int x, y, z;    
    char dir;       
    char o;

public:

    ChandraYaan3(int &ix, int &iy, int &iz, char &id, char org)
    {
        x = ix;
        y = iy;
        z = iz;
        dir = id;
        o = org;
    }

    // Moving Backward ChandraYaan3
    void Backward() 
    {
        switch (dir)
        {
        case 'N':
            y--;
            break;
        case 'S':
            y++;
            break;
        case 'E':
            x--;
            break;
        case 'W':
            x++;
            break;
        case 'U':
            z--;
            break;
        case 'D':
            z++;
            break;
        }
    }

    // Moving Forward ChandraYaan3
    void Forward() 
    {
        switch (dir)
        {
        case 'N':
            y++;
            break;
        case 'S':
            y--;
            break;
        case 'E':
            x++;
            break;
        case 'W':
            x--;
            break;
        case 'U':
            z++;
            break;
        case 'D':
            z--;
            break;
        }
    }

    // Moving ChandraYaan3 left
    void left() 
    {
        switch (dir)
        {
        case 'N':
            dir = 'W';
            o = 'W';
            break;
        case 'S':
            dir = 'E';
            o = 'E';
            break;
        case 'E':
            dir = 'N';
            o = 'N';
            break;
        case 'W':
            dir = 'S';
            o = 'S';
            break;
        case 'D':
            if (o == 'N')
            {
                dir = 'W';
                o = 'W';
                break;
            }
            else if (o == 'S')
            {
                dir = 'E';
                o = 'E';
                break;
            }
            else if (o == 'E')
            {
                dir = 'N';
                o = 'N';
                break;
            }
            else
            {
                dir = 'S';
                o = 'S';
                break;
            }
        case 'U':
            if (o == 'N')
            {
                dir = 'W';
                o = 'W';
                break;
            }
            else if (o == 'S')
            {
                dir = 'E';
                o = 'E';
                break;
            }
            else if (o == 'E')
            {
                dir = 'N';
                o = 'N';
                break;
            }
            else
            {
                dir = 'S';
                o = 'S';
                break;
            }
        }
    }

    // Moving ChandraYaan3 Right
    void right() 
    {

        switch (dir)
        {
        case 'N':
            dir = 'E';
            o = 'E';
            break;
        case 'S':
            dir = 'W';
            o = 'W';
            break;
        case 'E':
            dir = 'S';
            o = 'S';
            break;
        case 'W':
            dir = 'N';
            o = 'N';
            break;
        case 'D':
            if (o == 'N')
            {
                dir = 'E';
                o = 'E';
                break;
            }
            else if (o == 'S')
            {
                dir = 'W';
                o = 'W';
                break;
            }
            else if (o == 'E')
            {
                dir = 'S';
                o = 'S';
                break;
            }
            else
            {
                dir = 'N';
                o = 'N';
                break;
            }
        case 'U':
            if (o == 'N')
            {
                dir = 'E';
                o = 'E';
                break;
            }
            else if (o == 'S')
            {
                dir = 'W';
                o = 'W';
                break;
            }
            else if (o == 'E')
            {
                dir = 'S';
                o = 'S';
                break;
            }
            else
            {
                dir = 'N';
                o = 'N';
                break;
            }
        }
    }

    // Moving ChandraYaan3 Up
    void up() 
    {
        if (dir != 'U')
        {
            dir = 'U';
        }
    }

    // Moving ChandraYaan3 Down
    void down() 
    {
        if (dir != 'D')
        {
            dir = 'D';
        }
    }

    // x,y,z co-ordinates and dir
    void Pos()
    {
        cout << "Current Position: (" << x << ", " << y << ", " << z << "), direction: " << dir << endl;
    }

    // Final Position of ChandraYaan3
    void fPos()
    {
        cout << "Final Position: (" << x << ", " << y << ", " << z << ")" << endl;
    }

    // Final dir of ChandraYaan3
    void fd()
    {
        cout << "Final direction: " << dir << endl;
    }
};

int main()
{
    int x = 0, y = 0, z = 0;
    char dir = 'N';
    ChandraYaan3 CY3(x, y, z, dir, 'N');

    string s;
    cin >> s;
    cout << endl;
    // CY3.Pos();
    for (int i = 0; i < s.size(); i++)
    {
        char code = s[i];
        switch (code)
        {
        case 'f':
            CY3.Forward();
            CY3.Pos();
            break;
        case 'b':
            CY3.Backward();
            CY3.Pos();
            break;
        case 'l':
            CY3.left();
            CY3.Pos();
            break;
        case 'r':
            CY3.right();
            CY3.Pos();
            break;
        case 'u':
            CY3.up();
            CY3.Pos();
            break;
        case 'd':
            CY3.down();
            CY3.Pos();
            break;
        }
    }

    // CY3.Pos();
    cout << endl;

    CY3.fPos();
    cout << endl;

    CY3.fd();
    cout << endl;
    return 0;
}