# Lista-2.2

import numpy as np
# Questão 1
class My_array(np.ndarray):
    def __init__(self):
        self.array= np.empty(8, dtype=object)
        self.size= 0
    def __append__(self, something):
        if self.size+1<= len(self.array):
            self.array[self.size+1]= something
        else:
            backup= [i for i in self.array]
            self.array= np.empty(2*len(self.array), dtype=object)
            for i in backup:
                self.append(i)
            self.append(something)

a= My_array()
print(len(a.array))
    
# Questão 2
class ToroArray(np.ndarray):
    def __init__(self,l):
        self.array= numpy.array(l)
    
    def __new__(self,input_array):
        return ToroArray(input_array)
    
    def __getitem__(self,coord):
        return self.array[coord%len(self.array)]
tr= ToroArray([0,1,2,3,4,5,6,7,8,9])
print(tr[-36])
