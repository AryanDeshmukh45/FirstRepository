#include<iostream>
#include<string>
using namespace std;

class binary{
    string s; //******Default Private
    public:
    void read(void);
    void chk_bin(void);
    void ones(void);
    void display(void);

};
void binary :: read(void){
    cout<<"Enter the binary number: "<<endl;
    cin>>s;
}
void binary :: chk_bin(void){
    for(int i=0;i<s.length();i++){
        if(s.at(i)!='0'&& s.at(i)!='1'){
            cout<<"Not a binary Number";
            exit(0);
        }
    }
}
void binary :: ones(void){
    chk_bin();  //***NESTING OF MEMBER FUNCTION
    for(int i=0;i<s.length();i++){
        if(s.at(i)=='0'){
            s.at(i)='1';
        }
        else{
            s.at(i)='0';
        }
    }
}
void binary :: display(void){
    for(int i=0;i<s.length();i++){
        cout<<s.at(i);
    }
}
int main(){
    binary b;
    b.read();
    b.ones();
    b.display();
    return 0;
}