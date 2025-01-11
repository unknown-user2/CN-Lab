/* Formulae
	slope = (maxProb - minProb) / (maxQueueSize - threshold)	
	dropProb = minProb + slope * (curQueueLength - threshold)
 */

import java.util.*;

public class RED{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		
		System.out.print("Enter the number of packets to be sent: ");	
		int totalPackets = sc.nextInt();
		
		System.out.print("Enter the queue size: ");	
		int maxQueueSize = sc.nextInt();
	
		System.out.print("Enter the maximum probablity: ");	
		double maxProb = sc.nextDouble();
		
		System.out.print("Enter the minimum probablity: ");	
		double minProb = sc.nextDouble();
		
		System.out.print("Enter the threshold value: ");	
		int threshold = sc.nextInt();
		
		Random rand = new Random(System.currentTimeMillis());
		int curQueueLength = 0;
		
		for(int i=0; i<totalPackets; i++){
			//Calculate drop Probability
			double slope = (maxProb - minProb) / (maxQueueSize - threshold);
			double dropProb = minProb + slope * (curQueueLength - threshold);
			
			if(curQueueLength>=threshold && rand.nextDouble()<dropProb ){
				System.out.println("Packet Dropped!");
			} else {
				System.out.println("Packet Accepted" + (i+1));
				curQueueLength++;
			}
		}
	}
}
