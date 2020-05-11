#include <iostream>
#include <string>

using namespace std;

typedef long int l;

long int z_func(const string &s)
{
    l sum = 0;
    l length = s.length();
    l Z[length] = {0};
    l left = 0;
    l right = 0;
    for (l k = 1; k < length; ++k)
    {
        if (k > right) {
            left = right = k;
            while (right < length && s[right] == s[right - left]) {
                right ++;
            }
            Z[k] = right - left;
            right --;
        } else {
            int k1 = k - left;
            if (Z[k1] < right - k + 1) {
                Z[k] = Z[k1];
            } else {
                left = k;
                while (right < length && s[right] == s[right - left]) {
                    right ++;
                }
                Z[k] = right - left;
                right --;
            }
        }
    }

    for (l i = 0; i < length; ++i)
    {
        sum += Z[i];
    }

    return sum;
}

int main(int argc, char const *argv[])
{
    int T;
    cin >> T;
    while (T --) {
        string s;
        cin >> s;
        l res = z_func(s);

        cout << s.length() + res << endl;
    }

    return 0;
}
