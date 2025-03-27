import java.io.*;
import java.net.*;
import java.util.*;

class UDPClient {
    public static void main(String[] args) throws Exception {
    
        DatagramSocket clientSocket = new DatagramSocket();
        InetAddress IPAddress = InetAddress.getByName("localhost");
        byte[] sendData = new byte[1024];
        byte[] receiveData = new byte[1024];
	Scanner sc = new Scanner(System.in);
	  
        System.out.println("Enter the string in lowercase so that you receive the message in Uppercase from the server");
        String sentence = sc.nextLine();
        sendData = sentence.getBytes();
        DatagramPacket sendPacket = new DatagramPacket(sendData, sendData.length, IPAddress, 9876);
        clientSocket.send(sendPacket);

        DatagramPacket receivePacket = new DatagramPacket(receiveData, receiveData.length);
        clientSocket.receive(receivePacket);
        String modifiedSentence = new String(receivePacket.getData());
        System.out.println("FROM SERVER: " + modifiedSentence);

        clientSocket.close();
    }
}
