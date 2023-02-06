# Minor-Project1
Description:-
1) AffineCipher is a type of encryption and decryption method where we can combine the additive and
    multiplicative ciphers with a pair of keys to encrypt the message into ciphertext or decrypt the ciphertext to retrive the
    message.
2) The first key is used with the multiplicative cipher, the second key is used with the additive cipher.
3) Main method is used to get the keys, k1 and k2. As well as call the encrypt method or decrypt method.
4) Encrypt method takes 2 keys k1 and k2 and asks the user to input the message(plaintext) and converts it into ciphertext,
     using the formula:- C = (P × k1 + k2) mod 26 , where C is the cipher text & P is the message(plaintext).
5) Decrypt method also takes 2 keys k1 and k2 and asks the users to input the ciphertext(encoded message) and converts it
     into plaintext(decoded message) using the formula:- P = ((C − k2) × k1^-1) mod26, where C is the cipher text & P is the message.

Output:-
(for encryption)
enter key1:
5
enter key2:
5
to encrypt select (1), to decrypt select (2):
1
Enter the message:
Hello World
ciphertext is:Oziix Lxmiu

(for decryption)
 enter key1:
5
enter key2:
5
to encrypt select (1), to decrypt select (2):
2
Enter the chipertext:
Oziix Lxmiu
decrypted message is:Hello World
