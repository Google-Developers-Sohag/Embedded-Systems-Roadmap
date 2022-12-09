## Exercises on Loops in C:

> Note: 
> The exercises are prioritized in levels from the easiest to the hardest.

1) Write a program that adds some input numbers and terminates when the user enters zero and prints the sum of all the user inputs.

```bash

# to create a build directory
mkdir ./build 

# compile your source file into an executable
gcc ./calculator.c -o ./build/calculator.exe

# run the executable on your machine
./calculator.exe
```

```c

/**
* @brief: A program that adds some numbers and terminates when the user inputs zero.
* @author: mina_maher
* @refactoring: pavl_g
* @copyright: GDSC-Sohag
*/

#include<stdio.h> /* for FILE* stdin, FILE* stdout, printf(...), scanf(...) and setbuf(...) */

int main() {
    setbuf(stdout,NULL);

    double number, reads_number, sum = 0;

    /* body of loop is executed at least once*/
    do {
        printf("Enter a number: ");
        reads_number = scanf("%lf", &number);
        /* sanity check the input */
        if (reads_number <= 0) {
    	    printf("%s\n", "Please enter a valid number !");
    	    /* skip the rest and re-iterate back to the start */
            continue;
        }
        sum += number;
    } while (number != 0.0);

    printf("Sum = %.2lf",sum);

    return 0;
}
```

2) Write a C program to count number of digits in an Integer, for example '100' will produce an output of 3 digits. 

```bash
# to create a build directory
mkdir ./build 

# compile your source file into an executable
gcc ./digits_counter.c -o ./build/digits_counter.exe

# run the executable on your machine
./digits_counter.exe
```

```c
	
/**
* @brief: A program to count number of digits in an Integer, for example '100' will produce an output of 3 digits.
* @author: mina_maher
* @refactoring: pavl_g
* @copyright: GDSC-Sohag
*/

#define TRUE 1
#include<stdio.h> /* for FILE* stdin, FILE* stdout, printf(...), scanf(...) and setbuf(...) */

/**
 * The application entry point
 */
int main() {

    setbuf(stdout, NULL);
    int index = 0, number, reads_number;

    while (TRUE) {
	printf ("Enter number : ");
    	scanf("%d", &number);
        reads_number = scanf("%d", &number);
        /* sanity check the input */
        if (reads_number <= 0) {
    	    printf("%s\n", "Please enter a valid number !");
    	    /* skip the rest and re-iterate back to the start */
            continue;
        }
        while (TRUE) {
	    number = number / 10;
	    if (number > 0) {
		index++;
	    } else {
		index++;
		printf("number of digit : %d \n", index);
		/* to break the inner loop */
		break;
	    }
   	 }
	reads_number = 0;
	number = 0;
	index = 0;
    }
  return 0;
}
```

3) Write a C program to evaluate the summation equation (result = (1 / i) + (1 / i + 1) + (1 / i + 2) + ...; where i = [1, n] and n is the limit number for the summation).

```bash
# to create a build directory
mkdir ./build 

# compile your source file into an executable
gcc ./summation_generator.c -o ./build/summation_generator.exe

# run the executable on your machine
./summation_generator.exe
```

<br>

```c
/**
* @brief: A program to evaluate the summation equation  Σ (1 / i); where i = [1, n] and (n) is the limit.
* @author: mina_maher
* @refactoring: pavl_g
* @copyright: GDSC-Sohag
*/

#include<stdio.h> /* for FILE* stdin, FILE* stdout, printf(...), scanf(...) and setbuf(...) */

/**
 * The application entry point
 */
int main() {
    /* clear the standard output file */
    setbuf(stdout, NULL);
    
    /* declare and define variables for the equation */
    int number = 0;
    int reads_number = 0;
    float sum = 0;

    /* Create an endless state of user-inputs  */
    for (;;) {
        printf("Enter number n : ");
        /* clear the stdin buffer for a new input */
    	setbuf(stdin, NULL);
        reads_number = scanf("%d", &number);
        /* sanity check the input */
        if (reads_number <= 0) {
    	    printf("%s\n", "Please enter a valid number !");
    	    /* skip the rest and re-iterate back to the start */
            continue;
        }
        /* calculate the summation of (1 / i) equation */
	for (int i = 1; i <= number; i++) {
	     sum += (1.0 / i);
	     printf("%d %f \n", i, sum);
	}
	/* release the resources */
	number = 0;
	reads_number = 0;
	sum = 0;
    }
   return 0;
}
```
