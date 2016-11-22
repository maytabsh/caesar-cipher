# caesar-cipher
proj5

package proj5;
import java.util.*;

public class proj5
{
	public static void main(String[] args)
	{
		String running = "y";
		do {
		System.out.println("Enter the number of key values:");
		Scanner scan = new Scanner(System.in);
		int numKeys = scan.nextInt();
		System.out.println("Enter the individual key values (positive or negative integers, one after another in the same line with a blank between two values):");
		String keyValues = scan.nextLine();
		String[] keyValue = new String[numKeys];
		keyValue = keyValues.split(" ");
		for (int i=0; i<keyValue.length; i++)
		{
			int s = Integer.parseInt(keyValue[i]);
			enqueue(s);
		}
		System.out.println("Enter a string to be encoded:");
		String encode = scan.nextLine();
		String enc = encoded(encode);
		System.out.println("The encoded message:");
		System.out.println(enc);
		System.out.println("The decoded message:");
		String dec = decode(enc);
		System.out.println(dec);
		System.out.println("Another run of the program (y/n)?");
		running = scan.nextLine();
		}
		while (running != "n");
	}
	
	//encode
	public String encoded(String encode)
	{
		Node top = queue.peek();
		char c;
		for(int i=0; i<encode.length(); i++)
		{
			c = (char)(encode.charAt(i)+top.getItem());
			top = top.getNext();
		}
	}
	
	//decode
	public String decode(String decode)
	{
		Node top = queue.peek();
		char c;
		for(int i=0; i<encode.length(); i++)
		{
			c = (char)(encode.charAt(i)+top.getItem());
			top = top.getNext();
		}
	}
}
