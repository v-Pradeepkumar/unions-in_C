# unions-in_C



// union is a user defined datatype but unlike structure. structure uses different memory block but union use single memory. size of the union is taken according to the size  of the largest member of the union
#include <stdio.h>
union abc {
    int a ;
    char b ;
    double c ;
    float d ;
};
int main() {
    printf("%ld", sizeof(union abc)) ; //double has 8 byte which member has long among in union is the size of union
    return 0;
}




