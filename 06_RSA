import java.util.*;
import java.math.*;
import java.nio.charset.*;

public class RSA{
	public static void main(String[] args){
		BigInteger p,q,N,phi,e,d;
		
		p = BigInteger.probablePrime(1024,new Random());
		q = BigInteger.probablePrime(1024,new Random());
		N = p.multiply(q);
		phi = p.subtract(BigInteger.ONE).multiply(q.subtract(BigInteger.ONE));
		e = BigInteger.probablePrime(512,new Random());
		
		//e and phi should be co-prime (gcd of e and phi = 1 ) & 0 < e < phi
		while( phi.gcd(e).compareTo(BigInteger.ONE)>0 && e.compareTo(phi)<0){
			e = e.add(BigInteger.ONE);
		}
		
		d = e.modInverse(phi);
		
		System.out.println("Prime number p: "+ p);
		System.out.println("Prime number q: "+ q);
		System.out.println("Public key is: "+ e);
		System.out.println("Private key is: "+ d);
		
		Scanner sc = new Scanner(System.in);
		System.out.print("Enter the plain text: ");
		String testString = sc.nextLine();
		System.out.println("Encrypting String: "+ testString);
		
		byte[] encrypted = new BigInteger(testString.getBytes()).modPow(e,N).toByteArray();
		byte[] decrypted = new BigInteger(encrypted).modPow(d,N).toByteArray();
		

		System.out.print("Encrypted Bytes: ");
		for(int i=0; i<encrypted.length; i++){ 
			System.out.print(encrypted[i]); 
		}
		System.out.println();
		
		System.out.print("Decrypted Bytes: ");
		for(int i=0; i<decrypted.length; i++){ 
			System.out.print(decrypted[i]); 
		}
		System.out.println();
				
		System.out.println("Decrypted String: " + new String(decrypted, StandardCharsets.UTF_8));
	}
}
