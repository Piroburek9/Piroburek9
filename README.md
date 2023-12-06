#include <bits/stdc++.h>
typedef long long i64;
typedef int i32;
#define endl '\n'
#define pr pair<int, int>
#define fd(st, end, arr) for (int i = (st); i < (end); i++) {cout << arr[i] << " ";} cout << endl;
#define prs pair<int, string>
using namespace std;
const int inf = 1e9 + 7;
const i64 mod = 1073741824;
 
void optimization() {
    ios::sync_with_stdio(0);
    cin.tie(0);
    cout.tie(0);
}
 
int main() {
    optimization();
    int t;
    cin >> t;
    bool arr[1000001] = {};
    while(t--) {
        string s;
        cin >> s;
        for(int i = 0; i < s.size(); i++) {
            if(s[i] == 'b') {
                arr[i] = true;
                for(int j = i - 1; j >= 0; j--) {
                    if(s[j] >= 'a' && s[j] <= 'z') {
                        if(!arr[j]) {
                            arr[j] = true;
                            break;
                        }    
                    }
                }
            }
            if(s[i] == 'B') {
                arr[i] = true;
                for(int j = i - 1; j >= 0; j--) {
                    if(s[j] >= 'A' && s[j] <= 'Z') {
                        if(!arr[j]) {
                            arr[j] = true;
                            break;
                        }
                    }
                }
            }
        }
        for(int i = 0; i < s.size(); i++) {
            if(!arr[i]) {
                cout << s[i];
            }
        }
        cout << endl;
        fill_n(arr, 1000001, false);
    }
    return 0;
}
