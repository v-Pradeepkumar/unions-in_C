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




// accessing the member of union through pointers by using the (->) arrow operator  o/p >>90 Z
#include <stdio.h>
union abc {
    int a ;
    char b ;
} ;
int main() {
     union abc var ;
     var.a = 90 ;
     union abc *p = &var ;
     printf("%d %c", p-> a, p->b);
     return 0;
}






// find the size of union short > 2 bytes, float > 4 bytes, long > 8 bytes  o/p is 18 bytes
#include <stdio.h>

int main() {
    struct{
        short s[5] ;
        union {
            float y ;
            long z ;
        }u ;
    } t ;

    return 0;
}




