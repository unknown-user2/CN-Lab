import java.util.*;

//Frame class
class Frame {
	int num;
	String data;
	Frame(int user_num,String user_data){
		num = user_num;
		data = user_data;
	}
}

public class Frame_Sort{
	public static void main(String[] args){
	
		Scanner sc = new Scanner(System.in);
		System.out.print("Enter the number of frames: ");
		int n = sc.nextInt();
		Frame[] f = new Frame[n];
		
		for(int i=0;i<n;i++){
			System.out.print("Enter the frame number: ");
			int frame_num = sc.nextInt();
			System.out.print("Enter the frame data: ");
			String frame_data = sc.next();
			f[i] = new Frame(frame_num , frame_data);
		}
		
		//Bubble Sort
		for(int i=0;i<n;i++){
			boolean flag = false;
			for(int j=0;j<n-1;j++){
			
				if(f[j].num > f[j+1].num){
					Frame temp = f[j];
					f[j]=f[j+1];
					f[j+1] = temp;
					flag=true;
				}
				
				if(flag){
					break;	
				}
			}
		}
		
		//Print frames
		System.out.println("Sorted Frames at the reciever end: ");
		for(int i=0;i<n;i++){
			System.out.println(f[i].data);
		}
		
	}
}
