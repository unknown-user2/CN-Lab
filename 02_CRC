import java.util.*;

public class CRC{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		//Sender Side
		System.out.println("At Sender Side");
		System.out.print("Enter message bits: ");
		String message = sc.nextLine();
		System.out.print("Enter generator: ");
		String generator = sc.nextLine();
		
		int[] data = new int[message.length() + generator.length() - 1];
		int[] divisor = new int[generator.length()];
		
		for(int i=0; i<message.length(); i++){
			data[i] = Integer.parseInt(String.valueOf(message.charAt(i)));
		}
		
		for(int i=0; i<generator.length(); i++){
			divisor[i] = Integer.parseInt(String.valueOf(generator.charAt(i)));
		}
		
		//Add crc
		for(int i=0; i<message.length(); i++){
			if(data[i] == 1){
				for(int j=0; j<generator.length(); j++){
					data[i+j] = data[i+j] ^ divisor[j]; 
				}
			}
		}
		
		for(int i=0; i<message.length(); i++){
			data[i] = Integer.parseInt(String.valueOf(message.charAt(i)));
		}
		
		//Data + checksum
		System.out.println("The checksum code: ");
		for(int i=0; i<data.length; i++){
			System.out.print(data[i]);
		}
		System.out.println();
		
		
		
		//Reciever Side
		System.out.println("At Reciever Side");
		System.out.print("Enter checksum bits: ");
		message = sc.nextLine();
		System.out.print("Enter generator: ");
		generator = sc.nextLine();
		
		data = new int[message.length() + generator.length() - 1];
		divisor = new int[generator.length()];
		
		for(int i=0; i<message.length(); i++){
			data[i] = Integer.parseInt(String.valueOf(message.charAt(i)));
		}
		
		for(int i=0; i<generator.length(); i++){
			divisor[i] = Integer.parseInt(String.valueOf(generator.charAt(i)));
		}
		
		for(int i=0; i<message.length(); i++){
			if(data[i] == 1){
				for(int j=0; j<generator.length(); j++){
					data[i+j]= data[i+j] ^ divisor[j]; 
				}
			}
		}
		
		boolean flag=true;
		for(int i=0; i<data.length; i++){
			if(data[i]==1){
				flag=false;
				break;
			}
		}
		
		if(flag){
			System.out.println("Data Stream is valid");
		} else {
			System.out.println("Data Stream is invalid. CRC is error occured");
		}
 	}
}
