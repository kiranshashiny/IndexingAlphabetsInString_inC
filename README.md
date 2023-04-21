# Indexing_Alphabets_In_String_in_C_Programming



```
#include <stdio.h>
#include <string.h>
#include <ctype.h>
 
int main()
{
    char str[] = "Chikkodi - Sadalga             Ganesh Hukkeri";
    char alphabets [50];

    char *token;
    char needle [20];
    char constituency [50];
    char candidate    [50];
    int i,j;
    char ch;
    int found=0;
    
    strcpy (needle, "      ");
    strcpy (alphabets, "abcdefghijklmnopqrstuvwxyz");

    if ( (token = strstr(str, needle) ) == NULL ) {
	printf ("needle not found %s\n", needle);

    } else {
        printf (" Found Candidate name [>>>%s]\n", token );
	strcpy ( candidate, token );
    }
    printf ("Shashi Start Printing Indexes \n");
    for ( i=0; i< strlen ( alphabets) ; i++ ) {
	printf ("%3c", alphabets[i] );	
    }
    printf ("\n");
    for ( i=1; i< strlen ( alphabets)+1 ; i++ ) {
	printf ("%3d", i );	
    }
    printf ("\n");
    printf ("End\n");

    printf ("Shashi Start Printing Chikkodi \n");
    for ( i=0; i< strlen ( str) ; i++ ) {

	printf ("%3c", str[i] );	
    }
    printf ("\n");
    printf ("End\n");


    for ( i=0; i< strlen ( str) ; i++ ) {
		ch = tolower(str[i]);
	  	//printf ("Workingon >>>  %c ", ch ); 	
		found =0;
		for ( j=0; j<strlen(alphabets)+1; j++ ){
			if ( alphabets[j] == ch ){
				printf ("%3d", j+1 );	
				found=1;
				break;
			}
		}
		if ( found == 0 ){	
			printf ( "^^^" );	
		}
		//printf ( "\n");
    }
    printf ( "\n");

#if 0 

    for ( i=0; i< strlen ( str) ; i++ ) {
	printf ("%3c", str[i] ) ;
    }
    printf ("\n");

    for ( i=0; i< strlen ( str) ; i++ ) {
	printf ("%3d", i ) ;
    }
    printf ("\n");
    printf ("\n");
    printf ("\n");

    for ( i=0; i< strlen ( str) ; i++ ) {

	//printf ("%c ", str[i] ) ;
        if ( str[i] == ' ') 
 	   if ( str[i+1 ] == ' ')
 	       if ( str[i+2 ] == ' '){
	          printf ("Found three spaces at %d location \n", i );
    		  strncpy ( constituency, str, 18);
    		  constituency[i] = '\0';
		  break;
	       }
    }

    printf ( "\n");
    printf ( "Constituency = [%s] Candidate = [%s]\n", constituency, candidate );

#endif    
	
#if 0
    // Keep printing tokens while one of the
    // delimiters present in str[].
    while (token != NULL) {
        printf(" %s\n", token);
        token = strtok(NULL, " - ");
    }
#endif
 
    return 0;
}

```
