# Minor-Project1


import java.util.Scanner;

public class AffineCipher{

//main method
    
	public static void main(String[] args) {
		Scanner in=new Scanner(System.in);		
		System.out.println("enter key1:");
		int k1=in.nextInt();
		System.out.println("enter key2:");
		int k2=in.nextInt();
		System.out.println("to encrypt select (1), to decrypt select (2):");
		int choise=in.nextInt();		
		if (choise==1) {			
		    String ans1=Encrypt(k1,k2);
		    System.out.println("ciphertext is:"+ans1);
		}		
		else if(choise==2) {
		    String pt=Decrypt(k1,k2);
		    System.out.println("decrypted message is:"+pt);
		}
		in.close();
	}
	//encryption method
	public static String Encrypt(int key1,int key2) {
		Scanner in=new Scanner(System.in);
		System.out.println("Enter the message:");
		String ptext=in.nextLine();
		in.close();
		int k1=key1; 
	    int k2=key2; 
	    char[] ciphertext = new char[ptext.length()];    
	    for (int i = 0; i < ptext.length(); i++) {
	       char check1= ptext.charAt(i);
	       if(check1==' ') {
	    	  ciphertext[i]=' '; 
	       }
	       else if(Character.isUpperCase(check1)){
	            int k3 =ptext.charAt(i) - 'A'; 
	            int encrypted = (k3 * k1 +k2) % 26; 
	            ciphertext[i] = (char)(encrypted + 'A');
	          }
	       else {
	            int k3=ptext.charAt(i) - 'a';
	            int encrypted = (k3 * k1 +k2) % 26; 
	            ciphertext[i] = (char)(encrypted + 'a');
	          }
	        }
	        return new String(ciphertext);
	}
	//decryption method
	public static String Decrypt(int key1,int key2) {
		Scanner in=new Scanner(System.in);
		System.out.println("Enter the chipertext:");
		String ct=in.nextLine();
		in.close();
	    int k1 =key1 ; 
	    int k2 =key2 ; 
	    char[] plaintext = new char[ct.length()];
	    int k1_inverse = 0; 
	    for (int i = 0; i < 26; i++) {
	       if ((k1 * i) % 26 == 1) {
	          k1_inverse = i;
	          break;
	       }
	    }
	    for (int i = 0; i <ct.length(); i++) {
	          char check2 =ct.charAt(i);
	          if(check2==' ') {
		    	  plaintext[i]=' '; 
		       }
	          else if (Character.isUpperCase(check2)){
	            int k3 =ct.charAt(i) - 'A'; 
	            int decrypted = ((k3 - k2 + 26)* k1_inverse) % 26; 
	            plaintext[i] = (char)(decrypted + 'A');
	          }
	         else {
	            int k3 =ct.charAt(i) - 'a';
	            int decrypted = ((k3 - k2 + 26)* k1_inverse) % 26; 
	            plaintext[i] = (char)(decrypted + 'a');
	          }
	        }
	        return new String(plaintext);
	      }
}
