import java.util.*;

public class Leaky_Bucket{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		int received, sent, bucket_remaining=0;
		
		System.out.print("Enter the bucket capacity: ");
		int bucket_capacity = sc.nextInt();
		
		System.out.print("Enter bucket rate: ");
		int bucket_rate = sc.nextInt();
		
		System.out.print("Enter the number of packets to be sent: ");
		int n = sc.nextInt();
		
		int[] buf = new int[n];
		System.out.println("Enter each packet's size: ");
		for(int i=0; i<n; i++){
			buf[i]=sc.nextInt();
		}
		
		System.out.println("Time_t\t\tP_size\t\tAccepted\t\tSent\t\tRemaining");
		
		for(int i=0; i<n; i++){
			//Recieving
			if(buf[i]!=0){
				if(bucket_remaining + buf[i] > bucket_capacity){
					received=-1;
				} else {
					received = buf[i];
					bucket_remaining = bucket_remaining + buf[i];
				}
			} else {
				received=0;
			}
		
			//Sending
			if(bucket_remaining!=0){
				if(bucket_remaining < bucket_rate){
					sent = bucket_remaining;
					bucket_remaining=0;
				} else {
					sent = bucket_rate;
					bucket_remaining = bucket_remaining - bucket_rate;
				}
			
			} else {
				sent=0;
			}
			
			//Print
			if(received == -1){
				System.out.println((i+1)+"\t\t"+buf[i]+"\t\t"+"dropped"+"\t\t\t"+sent+"\t\t"+bucket_remaining);
			} else {
				System.out.println((i+1)+"\t\t"+buf[i]+"\t\t"+received+"\t\t\t"+sent+"\t\t"+bucket_remaining);
			
			}
		}
	}
}
