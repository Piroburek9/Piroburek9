#include <iostream>
using namespace std;
 
int main() {
    int v, t;
    cin >> v >> t;
    int distance = v * t;
    int res = (distance % 109 + 109) % 109;
    cout << res;
 
    return 0;
}
