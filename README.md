import java.lang.*;
import java.io.*;
import java.net.*;

class client {
   public static void main(String args[]) {
      try {
         Socket skt = new Socket("localhost", 1234);
	 BufferedReader br = new BufferedReader(new InputStreamReader (System.in));
         BufferedReader in = new BufferedReader(new
            InputStreamReader(skt.getInputStream()));
         System.out.println("enter the string: '");
	String line=br.readLine();
	PrintWriter out = new PrintWriter(skt.getOutputStream(), true);
	 out.print(line);



         in.close();
      }
      catch(Exception e) {
         System.out.print("Whoops! It didn't work!\n");
      }
   }
}
