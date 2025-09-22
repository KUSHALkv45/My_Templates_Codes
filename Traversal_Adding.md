class Solution {
    List<List<Integer>> adj;
    int[] ans;
    char[] req;
    public int[] countSubTrees(int n, int[][] edges, String labels) {
        req = labels.toCharArray();
        ans = new int[n];
        adj = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            adj.add(new ArrayList<>());
        }
        for (int[] i : edges) {
            adj.get(i[0]).add(i[1]);
            adj.get(i[1]).add(i[0]);
        }

        int[] a = new int[26];
        joseph(-1, 0, a);

        return ans;
    }

    private void joseph(int par, int node, int[] arr) {
        arr[req[node]-'a']++;
        for (int i : adj.get(node)) {
            if (i != par) {
                int[] a = new int[26];
                joseph(node, i, a);

                for(int j = 0 ; j < 26 ; j++){
                    arr[j] += a[j];
                }

            }
        }
        ans[node] = arr[req[node]-'a'];
    }


    

}
