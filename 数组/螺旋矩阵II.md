## leetcode 59

### c++ 
```
class Solution {
public:
    vector<vector<int>> generateMatrix(int n) {
        vector<vector<int>> result(n,vector<int>(n,0));
        int startx = 0, starty = 0;
        int loop = n / 2;
        int count = 1;
        int offset = 1;
        while(loop-- > 0){
            int i = startx, j = starty;
            for(; j < n - offset; j++){
                result[i][j] = count++;
            }
            for(;i < n - offset; i++){
                result[i][j] = count++;
            }
            for(;j>starty;j--){
                result[i][j] = count++;
            }
            for(;i>startx;i--){
                result[i][j] = count++;
            }
            startx++;
            starty++;
            offset++;
        }
        if(n%2 != 0){
            int mid = n / 2;
            result[mid][mid] = count;
        }
        return result;
    }
};
```

### java

```
class Solution {
    public int[][] generateMatrix(int n) {
        int[][] result = new int[n][n];
        int startx = 0, starty = 0;
        int loop = n / 2;
        int count = 1;
        int offset = 1;
        while(loop-- > 0){
            int i = startx, j = starty;
            for(; j < n - offset; j++){
                result[i][j] = count++;
            }
            for(;i < n - offset; i++){
                result[i][j] = count++;
            }
            for(;j>starty;j--){
                result[i][j] = count++;
            }
            for(;i>startx;i--){
                result[i][j] = count++;
            }
            startx++;
            starty++;
            offset++;
        }
        if(n%2 != 0){
            int mid = n / 2;
            result[mid][mid] = count;
        }
        return result;
    }
}
```