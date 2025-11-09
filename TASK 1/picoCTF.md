# Module Name
picoCTF
## Challenge Name
13

### Solve
**Flag:** `picoCTF{not_too_bad_of_a_problem}`

After learning caesar cipher, I had learnt to code it up in C. There were many issues at the beginning with my code, especially confusion with the segregation of lowercase and uppercase of my letters, after which I still had issues with my code, especially with special characters such as {,},_ being converted.


 For this i realised I had to add another argument with in my else if statement where a[i]<=90 and a[i]<=122 corresponding to the case of the character. My code checks for each character in the string, if the sum of its ascii code and the shift is lesser than or equal to the ascii code of the z/Z(lower case or uppercase depending on the compared character), then the letter is shifted by the shift value, since even after shifting it's still lies on the ascii range of the letters. but if the sum is greater than the ascii code of it's corresponding z, then it's ascii code is subtracted by (26-shift). 
 
 
 This way the shifting process is taken place, and at the beginning of making this program it ran perfectly when i inputted only characters, but it also meddled with special characters for which i had to modify the arguments of the else if statement. So this is how this program was created, and i was easily able to crack this challenge by simply copy pasting the string from the challenge and setting the shift value to 13(for ROT13).

### Program
#include <stdio.h>

int main()
{
    int n;
    char a[100];
    printf("Enter a string:\n");
    scanf("%s",a);
    printf("Enter shift number:\n");
    scanf("%d",&n);
    n=n%26;
    for(int i=0;a[i]!='\0';i++){
        if((a[i]>=65 && a[i]+n<=90) || (a[i]>=97 && a[i]+n<=122 ))
           a[i]+=n;
        else if((a[i]>=65 && a[i]+n>90 && a[i]<=90) || (a[i]>=97 && a[i]+n>122 && a[i]<=122))
           a[i]-=(26-n);
    }
    printf("%s",a);

    return 0;
}
```bash
Enter a string:
cvpbPGS{abg_gbb_onq_bs_n_ceboyrz}
Enter shift number:
13
picoCTF{not_too_bad_of_a_problem}
```

### New Learnings
Learnt Caesar Ciphering, honed my programming skills and had a short glimpse of cryptography.

### References 
https://www.geeksforgeeks.org/ethical-hacking/caesar-cipher-in-cryptography/

## Challenge Name
Mod 26

### Solve
**Flag:** `picoCTF{next_time_I'll_try_2_rounds_of_rot13_TLcKBUdK}`

Since I had my program ready from the above problem, all I had to do was copy paste the given string and execute it in the terminal.

### Program
#include <stdio.h>

int main()
{
    int n;
    char a[100];
    printf("Enter a string:\n");
    scanf("%s",a);
    printf("Enter shift number:\n");
    scanf("%d",&n);
    n=n%26;
    for(int i=0;a[i]!='\0';i++){
        if((a[i]>=65 && a[i]+n<=90) || (a[i]>=97 && a[i]+n<=122 ))
           a[i]+=n;
        else if((a[i]>=65 && a[i]+n>90 && a[i]<=90) || (a[i]>=97 && a[i]+n>122 && a[i]<=122))
           a[i]-=(26-n);
    }
    printf("%s",a);

    return 0;
}
```bash
Enter a string:
cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX}
Enter shift number:
13
picoCTF{next_time_I'll_try_2_rounds_of_rot13_TLcKBUdK}
```

### New Learnings
Implemented my program on Caesar Ciphering, honed my programming skills and had a short glimpse of cryptography.

### References 
https://www.geeksforgeeks.org/ethical-hacking/caesar-cipher-in-cryptography/

## Challenge Name
interencdec

### Solve
**Flag:** `picoCTF{caesar_d3cr9pt3d_86de32d2}`

This was a base64 decoding problem, which took me some time to realise until i encountered the == at the end, which means it was in the form of base64. So i used an online decoder to decode the base64 encrypted code to get another encrypted code within b'', which actually confused me because i did not know what it meant so i had to make a search for it. since i saw that it also ended in ==, it had to be decoded twice. after which i got something very similar to how a flag looks like, except there was no picoCTF in the beginning but it had some sort of curly braces, so i tried to see if ROT13 worked with my program but it didn't make sense because i was not getting the picoCTF part of my key, then i calculated the shift between the letter A and T,(my last three letters were JAM which ciphered to CTF when i shifted it by 19). After i figured out the shift was 19, i was able to find the flag.

BASE64

YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6ZzJhMnd6TW1zeWZRPT0nCg== decoded to
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg2a2wzMmsyfQ==' where d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg2a2wzMmsyfQ== decoded to
wpjvJAM{jhlzhy_k3jy9wa3k_86kl32k2}

CAESAR CIPHERING(SHIFT 19)
wpjvJAM{jhlzhy_k3jy9wa3k_86kl32k2} decoded to 
picoCTF{caesar_d3cr9pt3d_86de32d2}


### Program
#include <stdio.h>

int main()
{
    int n;
    char a[100];
    printf("Enter a string:\n");
    scanf("%s",a);
    printf("Enter shift number:\n");
    scanf("%d",&n);
    n=n%26;
    for(int i=0;a[i]!='\0';i++){
        if((a[i]>=65 && a[i]+n<=90) || (a[i]>=97 && a[i]+n<=122 ))
           a[i]+=n;
        else if((a[i]>=65 && a[i]+n>90 && a[i]<=90) || (a[i]>=97 && a[i]+n>122 && a[i]<=122))
           a[i]-=(26-n);
    }
    printf("%s",a);

    return 0;
}
```bash
Enter a string:
wpjvJAM{jhlzhy_k3jy9wa3k_86kl32k2}
Enter shift number:
19
picoCTF{caesar_d3cr9pt3d_86de32d2}
```

### New Learnings
Learnt base64, and implemented my knowledge in caesar ciphering after decoding in base 64.

### References 
https://www.geeksforgeeks.org/ethical-hacking/caesar-cipher-in-cryptography/
https://www.base64decode.org/
