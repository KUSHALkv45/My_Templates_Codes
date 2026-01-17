```java
import java.util.*;
import java.lang.*;
import java.io.*;

import java.io.*;
import java.util.*;

public class Main {
    static FastReader in = new FastReader();
    static PrintWriter out = new PrintWriter(System.out);

    public static void main(String[] args) {
        int t = in.nextInt(); // Read number of test cases (modify as needed)
        while (t-- > 0) {
            solve();
        }
        out.flush(); // Ensure all output is printed
    }

    static void solve() {
        int n = in.nextInt();
        
        int q = in.nextInt();
        
        int [] arr = new int [n];
        for(int i = 0 ;i < n ; i++){
            arr[i] = in.nextInt();
        }
        
        
        for(int i = 0 ; i < q ; i++){
            int op = in.nextInt();
            int l = in.nextInt();
            int r = in.nextInt();
            
            
            
            if(op == 1){
                arr[l-1] = r;
            }
            else{
                
                int ans = 0;
                int min = arr[l-1];
                
                for(int d = 0 ; d <= r-l ; d++){
                    min = Math.min(min,arr[l-1+d]);
                    if(min == d){
                        ans = 1;
                        break;
                    }
                    else if(min < d){
                        break;
                    }
                }
                
                out.println(ans);
                
            }
            
            
            
        }
    }

    
    static class FastReader {
        BufferedReader br;
        StringTokenizer st;
        
        public FastReader() {
            br = new BufferedReader(new InputStreamReader(System.in));
        }
        
        String next() {
            while (st == null || !st.hasMoreElements()) {
                try {
                    st = new StringTokenizer(br.readLine());
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
            return st.nextToken();
        }
        
        int nextInt() { return Integer.parseInt(next()); }
        long nextLong() { return Long.parseLong(next()); }
        double nextDouble() { return Double.parseDouble(next()); }
        String nextLine() {
            String str = "";
            try {
                str = br.readLine();
            } catch (IOException e) {
                e.printStackTrace();
            }
            return str;
        }
    }
}
```

