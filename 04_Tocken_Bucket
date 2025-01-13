import java.util.*;

public class Tocken_Bucket{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		int sent ,bucket_remaining=0;
		
		System.out.print("Enter the bucket capacity: ");
		int bucket_capacity = sc.nextInt();
		
		System.out.print("Enter the tocken generation rate: ");
		int bucket_rate = sc.nextInt();
		
		System.out.print("Enter number of packets to be sent: ");
		int n = sc.nextInt();
		
		
		System.out.println("Time_t\t\tTocken_requested\tTocken_sent\tBucket_remaining");
		for(int i=0; i<n; i++){
			if(bucket_rate + bucket_remaining > bucket_capacity){
				sent = bucket_capacity - bucket_remaining;
				bucket_remaining = bucket_capacity;
			} else {
				sent = bucket_rate;
				bucket_remaining = bucket_remaining + bucket_rate;
			}
			System.out.println((i+1)+"\t\t"+bucket_rate+"\t\t\t\t"+sent+"\t\t"+bucket_remaining);
		}
	}
}
