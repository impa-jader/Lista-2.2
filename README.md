# Lista-2.2

import numpy as np
# Questão 1
class My_array:
    def __init__(self):
        self.array= np.empty(8, dtype=object)
        self.size= 0
    def append(self, something):
        if self.size< len(self.array):
            self.array[self.size]= something
            self.size+=1
        else:
            backup= self.array
            self.array= np.empty(2*len(self.array), dtype=object)
            for i in backup:
                self.append(i)
            self.append(something)


    
# Questão 2
class ToroArray(My_array):
    def __init__(self,l):
        super().__init__()
        self.array= np.array(l)
        
    def __getitem__(self,coord):
        return self.array[coord%len(self.array)]


if __name__=="__main__":
    tr= ToroArray([0,1,2,3,4,5,6,7,8,9])
    print(tr[-36])
    a= My_array()
    print(len(a.array))
