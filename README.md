import numpy as np
# Questão 1
class My_array:
    def __init__(self):
        self.array= np.empty(1, dtype=object)
        self.size= 0
    def append(self, something):
        if self.size< len(self.array):
            self.array[self.size]= something
            self.size+=1
        else:
            backup= self.array
            self.array= np.empty(2*len(self.array), dtype=object)
            self.size=0
            for i in backup:
                self.append(i)
            self.append(something)
    def __str__(self):
        return str(self.array)


    
# Questão 2
class ToroArray(My_array):
    def __init__(self,l):
        super().__init__()
        self.array= np.array(l)
        
    def __getitem__(self,coord):
        return self.array[coord%len(self.array)]


if __name__=="__main__":
   tr=ToroArray([10,11,12,13,14])
   print(tr[6])
   print (tr[-20])
   a= My_array()
   a.append(1)
   print(a)
   a.append(2)
   print(a)
   a.append(3)
   print(a)
