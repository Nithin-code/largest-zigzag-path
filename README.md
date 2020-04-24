# largest-zigzag-path
java code to find largest zig zag sequence


import java.util.*;
import java.lang.*;
import java.io.*;
import java.math.*;
class ABC
 {
	public static void main (String[] args)
	 {
	   //code
	   Scanner sc = new Scanner(System.in);
	   int t = sc.nextInt();
	   while(t-->0){
	       int n = sc.nextInt();
	       int M[][] = new int[n][n];
	       int dp[][] = new int[n][n];
	       for(int i=0;i<n;i++){
	           for(int j=0;j<n;j++){
	               M[i][j]= sc.nextInt();
	               dp[i][j] = M[i][j];
	           }
	       }
	       for(int i=1;i<n;i++){
	           
	           for(int j=0;j<n;j++){
	               int max =0;
	               for(int k=0;k<n;k++){
	                 if(k!=j){
	                  if(max<dp[i-1][k]){
	                     max = dp[i-1][k];
	                     }
	                 }
	                }
	                dp[i][j] = max+M[i][j];
	           }
	       }
          int m =0;
          for(int j=0;j<n;j++){
              if(m<dp[n-1][j]){
                  m = dp[n-1][j];
              }
          }
          System.out.println(m);
	   }
	 }
}
