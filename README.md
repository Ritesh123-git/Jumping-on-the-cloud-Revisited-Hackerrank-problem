# Jumping-on-the-cloud-Revisited-Hackerrank-problem
Hackerrank Problem
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    // Complete the jumpingOnClouds function below.
    static int jumpingOnClouds(int[] c, int k) {
         int energy=100;
         int i=0;
         int p=k;
         int n=c.length;
         int l=0;
         int jumping_value=c[(i+k)%n];
         while((i+k)%n!=0){
              jumping_value=c[(i+k)%n];
             if(jumping_value==1){
                 energy=energy-3;
             }
             else{
                 energy=energy-1;
             }
             k=k+p;
             l=k;
         }
         if(c[(i+l)%n]==1){
             return energy-3;
         }
         else{
         return energy-1;
         }


    }

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) throws IOException {
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        String[] nk = scanner.nextLine().split(" ");

        int n = Integer.parseInt(nk[0]);

        int k = Integer.parseInt(nk[1]);

        int[] c = new int[n];

        String[] cItems = scanner.nextLine().split(" ");
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        for (int i = 0; i < n; i++) {
            int cItem = Integer.parseInt(cItems[i]);
            c[i] = cItem;
        }

        int result = jumpingOnClouds(c, k);

        bufferedWriter.write(String.valueOf(result));
        bufferedWriter.newLine();

        bufferedWriter.close();

        scanner.close();
    }
}
