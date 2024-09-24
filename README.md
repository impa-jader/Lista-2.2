# Lista-2.2

# Questão 2
import numpy
class ToroArray:
    def __init__(self,l):
        self.array= numpy.array(l)
    
    def __getitem__(self,coord):
        return self.array[coord%len(self.array)]
tr= ToroArray([0,1,2,3,4,5,6,7,8,9])
print(tr[12])
