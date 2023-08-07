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






// comparision of using union instead of structures
#include <stdio.h>
typedef union {
    int a ;
    char b ;
    double c ;  //size of union 8 bytes
} data ;        
int main() {
    data arr[10];
    arr[0].a = 10 ;    //size = 80 bytes
    arr[1].b = 'a' ;
    arr[2].c = 10.178 ;
    

    return 0;
}

typedef struct{
    int a ;
    char b ;
    double c;       // size of this structure is 13 byte
}data ;
int main () 
{
    data arr[10];
    arr[0].a = 10 ;     //size 130 bytes
    arr[1].b = 'a' ;
    arr[2].c = 10.178 ;
}







                    
                       ** ENUMERATION**

                        
// enumerator is also a user defined type which is used to assign names to integral constants because names are easier to handle in program. o/p >> 1

#include <stdio.h>
enum Bool {false , true};
int main() {
    enum Bool var ;
    var = true ;
    printf("%d", var);
    return 0;
}







// find the o/p >> 0 0 0
#include <stdio.h>

int main() {
    enum point {x = 0, y = 0, z = 0};
    printf("%d %d %d", x, y, z);
    return 0;
}





// find the o/p >> 0 0 0 1 
#include <stdio.h>

int main() {
    enum point {x = 0, c, y = 0, z = 0};
    printf("%d %d %d %d", x, y, z, c);      //in enum any var get value +1 of before variable
    return 0;
}





// find the o/p >> integer error
#include <stdio.h>

int main() {
    enum point {x = 0, y = 2.5, z = 0};
    printf("%d %d %d ", x, y, z);      //only integral values are allowed(integer only)
    return 0;
}






//example of structure calculating area of rectangle using structure
/*
i/p >> enter the upper left coordinates of the rectangle: 
3 8
i/p >> enter the lower right coordinates of the rectangle: 
14 2
o/p >> Area of rectangle: 66
*/


#include <stdio.h>

struct point{
    int x ;
    int y ;
};

struct rectangle{
    struct point upper_left;
    struct point lower_right;
}; 
int area(struct rectangle r)
{
    int length, breadth ;
    length = r.lower_right.x - r.upper_left.x ;
    breadth = r.upper_left.y - r.lower_right.y ;
    
    return length * breadth ;
    
}
int main() {
    struct rectangle r ;
    printf("enter the upper left coordinates of the rectangle: \n");
    scanf("%d %d", &r.upper_left.x, &r.upper_left.y) ;
    printf("enter the lower right coordinates of the rectangle: \n");
    scanf("%d %d", &r.lower_right.x, &r.lower_right.y) ;
    printf("Area of rectangle: %d", area(r));
    return 0;
}
