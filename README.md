# 118.-Pascal-s-Triangle

````py
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        
        ans = [[1], [1,1]]

        for row_num in range(2, numRows):
            # formatted excluded 2 from side
             # start from next row e.g. 3rd row 
            els = row_num + 1
            row  = [1] + [0 for i in range(els - 2)] + [1]  #exclude 2 elements
            for j in range(1, els-1):
                row[j] = ans[row_num - 1][j-1] + ans[row_num - 1][j]
            ans.append(row)
        return ans[0: numRows]
````
