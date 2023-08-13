# 118.-Pascal-s-Triangle

````py
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        res = [[1]] # List[List[int]] base 1
        for i in range(numRows-1): # as above one is already created
            #prepare to create new row
            temp = [0] + res[-1] + [0] # res[-1]=[1,1]=> [0,1,1,0]
            row = [] # new row
            # res[-1] represent last list of res
            # need to be 1 more element in range
            for j in range(len(res[-1]) + 1): # 2 + 1   
                row.append(temp[j] + temp[j+1] ) # row = [1, 2, 1]
            res.append(row)
        return res
            


````
