```java
 int max = 1;
        
        // return s.length() == 1 ? 1 : s.length() == 2 ? s.charAt(0) == s.charAt(1) ? 2 : 1;
        if(s.length() == 1 ){return s;}
        if(s.length() == 2){
            return s.charAt(0) == s.charAt(1) ? s : s.substring(0,1) ;
        }
        int n = s.length();
        
        boolean [][] lps = new boolean [n+1][n+1];
        
        int len = 1; int idx = 0;
        
        for(int i = 0 ; i < n ; i++){
            lps[i][i] = true;
            if(i + 1 < n && s.charAt(i) == s.charAt(i+1)){
                lps[i][i+1] = true;
                if(len == 1){
                    len = 2;
                    idx = i;
                }
            }
        }
        
        for(int j = 2 ; j < n ; j++){
            for(int i = 0 ; i < n ; i++){
                if(i + j < n && s.charAt(i) == s.charAt(i+j) && lps[i+1][i+j-1]){
                    lps[i][i+j] = true;
                    if(j+1 > len){
                        len = j+1;
                        idx = i;
                    }
                }
            }
        }
        
        // System.out.println(Arrays.deepToString(lps));
        
        return s.substring(idx,len+idx);
```







