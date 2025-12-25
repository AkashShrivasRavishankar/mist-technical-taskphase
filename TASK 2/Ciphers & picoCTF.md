# Cipher Name
Hill Cipher
## Explanation

### Encryption

Hill Cipher works on two given terms, plaintext and key such that, if the length of plaintext is some positive integer n, then the length of the key is n^2 or n square.

The way hill cipher works is that alphabets from A to Z are labelled 0 upto 25. The alphabet of each plaintext is then substiuted by it's corresponding numerical value and arranged in a column matrix, the same is done with the key and a square matrix is formed in such a manner that the first row is the first n letters, the next row is the proceeding n letters and so on.

We know that the dimensions of the plaintext matrix is n x 1 and the dimensions of the key matrix is n x n. now we multiply the key matrix with the plaintext matrix(not the other way around)
and we obtain a new column matrix. This is the ciphered matrix. By taking each respective number and performing mod 26 on each number, and finding it's character equivalent, the ciphertext can be encoded. The code in C for encryption is given in the program given below

### Decryption
We know that the multiplication of the Key matrix with the plaintext gives us ciphered matrix i.e [KEY][PLAINTEXT]=[CIPHERED]. Now since we know the key, we can multiply the inverse of the key matrix with the ciphered matrix to obtain the plaintext. We also take mod of 26 in each and every step according to the principle of hill cipher.

Thus the formula becomes [KEY]^-1[CIPHERED] = [PLAINTEXT]. 

Thus we first convert the ciphered text back into its numerical equivalent and place it in a column matrix, we take the inverse of the key matrix(and mod 26 each element) and then multiply the inverse of the key matrix with the ciphered matrix. 

Thus we will get a matrix on multiplication, which after taking mod of 26 with each element will provide the desired plaintext matrix, which on conversion to its character equivalents, will provide plaintext.
### Program
#include <stdio.h>


```bash
int main()
{
    const int n=3;
    char pt[n+1],key[n*n+1],ct[n+1];
    printf("USING CAPITAL LETTERS ONLY\n\n\n");
    printf("Enter plain text of size %d\n",n);
    scanf("%s",pt);
    printf("Enter key of size %d\n",n*n);
    scanf("%s",key);
    //multiplying matrices
    int p[n][1],k[n][n],c[n][1];
    int rp=n,cp=1;
    int rk=n,ck=n;
    int rc=n,cc=1;
    for(int i=0;i<rp;i++)
       for(int j=0;j<cp;j++)
          p[i][j]=(int)(pt[i]-65); 
    int x=0;
    for(int i=0;i<rk;i++)
       for(int j=0;j<ck;j++)
          k[i][j]=(int)(key[x++]-65);  
    for(int i=0;i<rk;i++){
       for(int j=0;j<cp;j++){
         c[i][j]=0;
         for(int k1=0;k1<ck;k1++){
           c[i][j]+=k[i][k1]*p[k1][j];
           c[i][j]%=26; }}}
    for(int i=0;i<n;i++)
       ct[i]=(char)(c[i][0]+65);
    ct[n]='\0';
    printf("\nCiphered Text:  %s \n",ct);
         
    
}
```
### New Learnings
Learnt Hill Ciphering, and tested my programming skills.

### References 
https://www.geeksforgeeks.org/dsa/hill-cipher/

# Cipher Name
Rail Fence Cipher
## Explanation

### Encryption

In a Rail Fence Cipher, There's an input sentence and a key value. From these two values the ciphered output is rearranged in a zig-zag manner. The key value is the step value; let's say the value of the key is 3, then every 3rd character from the beginning acts as a 'rail', and the first character begins as the 'fence' of the entire sentence. Thus oblique lines going from the fences to the rails and back from rails to fences, forms a zigzag pattern. In this manner, the characters of the sentences are plotted on a grid.

After plotting these characters on a grid, The ciphered text is written in such a way that the first row is read, and the second row is appended, and so on till the all the rail elements are appended. Thus in this manner, the rail fence cipher is performed. The length of the input sentence is equal to the length of the ciphered text

### Decryption
We now implement the last sentence of the Encryption in order to decrypt the ciphered text. First with the help of the key value and the length of the ciphered text, we create a blank zig zag pattern on a grid till the number of columns is equal to the length of the ciphered text. now we place the first few elements in the first row with the step of n columns, where n is the value of the key.

in a similar manner we now place the proceeding characters in the next row, from left to right in the highlighted zigzag boxes done in the first step. We do this till we finally approach the rails and once the whole process is done, we can find the decrypted text by reading the whole string in a left to right zig zag manner.

### New Learnings
Learnt and understood Rail Fence Ciphering.

### References 
https://www.geeksforgeeks.org/dsa/rail-fence-cipher-encryption-decryption/

# Cipher Name
Affine Cipher
## Explanation

### Encryption

Affine cipher converts each character to another character as per the formula 
E(x)=(ax+b) mod m where a and b are two known key value positive integers and x is the number equivalent of a letter(A corresponds to 0, B corresponds to 1 and so on till Z corresponds to 25). m is the total number of letters which in this case is 26. a and m must be co-prime numbers. Using this formula, E(x) acts as a function that returns an output for each input number equivalent of a letter, thus encrypting each character.

For example let's take a and b as 17 and 20
then taking the character T which corresponds to it's number value 19, when substituted in the encryption formula gives 5 i.e [17*(19)+20] mod 26 = 5. this way 'TWENTY FIFTEEN' can be encypted to 'FEKHFM BABFKKH'.

### Decryption
In a similar manner of encrypted, there is a formula of decryption which is basically the inverse of the encryption function while keeping in mind the laws of modular arithmetic properties.
Earlier we saw that a and m must be coprime, the reasoning for this will be explained ahead.

By now treating y as x and x as y in the encryption function we can find the decryption function. thus let E(x) be x now and x be y i.e D(x), thus x = (ay+b) mod m, subtracting b on both sides we get, x-b = ay mod m, now we cannot divide by a on both sides because when there is a presence of mod, division becomes meaningless, thus we multiply both sides with a inverse which the modular multiplicative inverse i.e a * a^-1 mod m = 1, where a and m have a greatest common divisor of 1 for this to hold true. We require these conditions in order to separate out y i.e D(x). thus multiplying both sides with a inverse we get D(x) = a^-1 (x-b) mod m

If a = 17, then a inverse = 23 such that 17*23 mod 26 gives 1.

thus on backsubstitution of 'FEKHFM BABFKKH' we get 'TWENTY FIFTEEN'.

### New Learnings
Learnt and understood Affine Cipher.

### References 
https://www.geeksforgeeks.org/dsa/implementation-affine-cipher/


# Module Name
picoCTF
## Challenge Name
Rail-fence

### Solve
**Flag:** `picoCTF{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_D00AFDD3}`

After understanding rail fence cipher, I opened the text file from the challenge, and I used an online website in order to decrypt the text given in the file as I knew that the key value of the rail fence cipher varies and I would be able to change it easily in the website, I kept the mode in the website to 'decode' and varied the key value till I got the flag when I set the key value to 4. Thus on keeping the key value at 4 the website printed 'The flag is: WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_D00AFDD3'.

### New Learnings
Learnt Rail Fence Ciphering the implemented its usage in the challenge.

### References 
https://cryptii.com/pipes/rail-fence-cipher
## Challenge Name
Guess My Cheese (Part 1)

### Solve
**Flag:** `picoCTF{ChEeSy86ec32f4}`

This challenge had a lot of failures at the beginning because I was firstly thinking It would be solved by rail fence cipher or maybe hill cipher as affine cipher required two variables. Later on, no matter what I typed in encrypt cheese, the code always said it didn't consume that cheese. So after a long time it hit me that I should start typing types of cheese, so I started typing MOZZARELLA, LEICESTER, GORGONZOLA, CHEDDAR etc. I never thought of using affine cipher as I believed solving equations with mod would be difficult, so within just the free 2 encryptions the code provided, I tried to perform one-one mapping on the given encrypted code to decode. But It was impossible since there were always some missing alphabets ending up in a guess-game. Finally after doing some research, I realised that equations are still solvable with modulus involved in it. 

Thus after figuring out that all the letters had a one to one mapping, i made the user of affine ciphering. By guessing LEICESTER, i found that L and E corresponded to B AND W. then I solved the equations 
11A + B = 1 MOD 26
4A + B = 22 MOD 26
on subtracting equation 2 from 1,
 we get 7A = -21 mod 26
which gives us 7A = 5. We know that modular multiplicative inverse of 7 is 15. So we get 
A = 15*5 mod 26 which gives us the value of A as 23. by substituting A in equation 2 we get 
B = 22 - 4*23 mod 26
B = -70 mod 26
B = 8
thus by plotting A and B as 23 and 8 on an affine ciphering website, the encryption of LE corresponded to BW, now by going into the DECODE mode and writing down the encrypted cheese, I decrypted the cheese and found the flag.

### New Learnings
Learnt Affine Ciphering and it's working, and implemented it several times.

### References 
https://cryptii.com/pipes/affine-cipher

