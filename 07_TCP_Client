import java.util.*;
import java.net.*;
import java.io.*;

public class TCP_Client{
	public static void main(String[] args) throws Exception{
		Scanner sc = new Scanner(System.in);
		Socket sock = new Socket("127.0.0.1",4000);
		System.out.print("Enter file name: ");
		String fname = sc.nextLine();
		
		OutputStream ostream = sock.getOutputStream();
		PrintWriter pwrite = new PrintWriter(ostream,true);
		pwrite.println(fname);
		
		InputStream istream = sock.getInputStream();
		BufferedReader ContentRead = new BufferedReader(new InputStreamReader(istream));
		
		
		String str;
		while((str = ContentRead.readLine())!=null){
			System.out.println(str);
		}
	}
}
