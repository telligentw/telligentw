#include <iostream>
using namespace std;
#define MaxSize 50
typedef int ElemType;
typedef struct{
    ElemType data[MaxSize];
    int top;
}SqStack;
void stack_init(SqStack &S){
    S.top = -1;
}
bool stack_empty(SqStack S){
    if(S.top == -1){
        return true;
    }return false;
}
bool Push(SqStack &S,ElemType e){
    if(S.top == MaxSize){
        return false;
    }
    S.data[++ S.top] = e;
    return true;
}
bool Pop(SqStack &S,ElemType &e){
    if(stack_empty(S)){
        return false;
    }
    e = S.data[S.top--];
    return true;
}
bool get_top(SqStack S,ElemType &e){
    if(stack_empty(S)){
        return false;
    }
    e = S.data[S.top];
    return true;
}
int main(){
    SqStack S;//先进后出FILO
    stack_init(S);
    bool flag;
    flag = stack_empty(S);
    if(flag){
        cout << "stack is empty" << endl;
    }
    Push(S,3);
    Push(S,4);
    Push(S,5);
    ElemType e;
    flag = get_top(S,e);
    if(flag){
        cout << "get top" << " " << e << endl;
    }
    flag = Pop(S,e);
    if(flag){
        cout << "pop element" << " " << e << endl;
    }
    return 0;
}
