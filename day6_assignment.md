//1. PALINDROME
#include<iostream>
#include<string>
using namespace std;

int main(){
    string str;
    cout<<"Enter a string:";
    cin>>str;
    string rev=str;
    reverse(rev.begin(),rev.end());
    if (str==rev){
        cout<<"The string is a palindrome."<<endl;
    }
    else{
        cout<<"the string is not a palindrome."<<endl;
    }
    return 0;
}


//2.ANAGRAM
#include<iostream>
#include<string>
#include<algorithm> 
using namespace std;

int main(){
    string str1, str2;
    cout<<"Enter first string:";
    cin>>str1;
    cout<<"Enter second string:";
    cin>>str2;
    sort(str1.begin(),str1.end());
    sort(str2.begin(),str2.end());
    if (str1==str2){
        cout<<"The strings are anagrams."<<endl;
    }
    else{
        cout<<"The strings are not anagrams."<<endl;
    }
    return 0;
}

//3. pangram
#include<iostream>      
#include<string>
using namespace std;
int main(){
    string str;
    cout<<"Enter a string:";
    cin.ignore();
    getline(cin,str);
    bool isPangram = true;
    for(char ch='a';ch<='z';ch++){
        if(str.find(ch)==string::npos && str.find(toupper(ch))==string::npos){
            isPangram = false;
            break;
        }
    }
    if(isPangram){
        cout<<"The string is a pangram."<<endl;
    }
    else{
        cout<<"The string is not a pangram."<<endl;
    }
    return 0;
}

//4 ISOGRAM
#include <iostream>
#include <set>
#include <algorithm>
using namespace std;

int main(){
    string str;
    cout<<"Enter a string:";
    cin>>str;
    set<char> s;
    for(char ch:str){
        ch=tolower(ch);
        if(s.count(ch)){
            cout<<"The string is not an isogram."<<endl;
            return 0;
        }
        s.insert(ch);
    }
    cout<<"The string is an isogram."<<endl;
    return 0;
}

//5. heterogram
#include <iostream>
#include <set>
#include <algorithm>
using namespace std;

int main(){
    string str;
    cout<<"Enter a string:";
    cin>>str;
    set<char> s;
    for(char ch:str){
        ch=tolower(ch);
        if(s.count(ch)){
            cout<<"The string is not a heterogram."<<endl;
            return 0;
        }
        s.insert(ch);
    }
    cout<<"The string is a heterogram."<<endl;
    return 0;
}

//6. semodnilap
#include <iostream>
#include <algorithm>
using namespace std;
int main(){
    string str;
    cout<<"Enter a string:";
    cin>>str;
    string rev=str;
    reverse(rev.begin(),rev.end());
    if (str==rev){
        cout<<"The string is not a semordnilap."<<endl;
    }
    else{
        cout<<"The string is a semordnilap."<<endl;
    }
    return 0;
}

//7. acronym
#include <iostream>
#include <sstream>
using namespace std;

int main() {
    string phrase;
    getline(cin, phrase);

    stringstream ss(phrase);
    string word;

    while(ss >> word) {
        cout << (char)toupper(word[0]);
    }

    return 0;
}

//8. lipogram
#include <iostream>
#include <string>
using namespace std;

int main() {
    string str;
    char ch;

    getline(cin, str);

    cout << "Enter missing letter: ";
    cin >> ch;

    bool found = false;

    for(char c : str) {
        if(tolower(c) == tolower(ch)) {
            found = true;
            break;
        }
    }

    if(found)
        cout << "Not Lipogram";
    else
        cout << "Lipogram";

    return 0;
}


//9.abecedarian

#include <iostream>
#include <string>
using namespace std;

int main() {
    string str;
    cin >> str;

    bool flag = true;

    for(int i = 1; i < str.length(); i++) {
        if(str[i] < str[i - 1]) {
            flag = false;
            break;
        }
    }

    if(flag)
        cout << "Abecedarian";
    else
        cout << "Not Abecedarian";

    return 0;
}

//10.antigram

#include <iostream>
#include <string>
using namespace std;

int main() {
    string s1, s2;

    cin >> s1 >> s2;

    bool antigram = true;

    for(char c1 : s1) {
        for(char c2 : s2) {
            if(tolower(c1) == tolower(c2)) {
                antigram = false;
                break;
            }
        }
    }

    if(antigram)
        cout << "Antigram";
    else
        cout << "Not Antigram";

    return 0;
}