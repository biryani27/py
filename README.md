# py

def linear(a,arr):
    for i in range(len(arr)):
        if(arr[i]==a):
            print(a,"is found at index",i+1)
            return
    print("not found")
linear(44,[2,3,4,44])


def binary (a,arr):
    low = 0
    high = len(arr)-1
    while(low<high):
        mid=int((low+high)/2)
        if(arr[mid]>=a):
            high=mid
        else:
            low=mid+1
        if(arr[low]==a):
            print(a,"element found at",low)  
(binary(8,[1,4,7,8])) 


import bisect
def insert(list,n):
    bisect.insort(list,n)
    return list
list = [1,2,3,5,4]
n=3
print(insert(list,n))
list.sort()
print(list)


size= 3
stack=[size]
while True:
        x=int(input("\n 1.push \n 2.pop \n 3.Display \n 4.Exit \n\n"))
        if x==1:
                if len(stack)>3:
                        print("Stack  is overflow")
                else:
                        val = int(input("Enter number to insert"))
                        stack.append(val)
        elif x==2:
                if len(stack)<1:
                        print("stack is underflow")
                else:
                        stack.pop()
        elif x==3:
                print(stack)
        elif x==4:
                break
        else:
                print("invalid input")      




file = open('file.txt', 'r')
for each in file:
	print (each)

file = open("file.txt", "w")
print(file.write("This is write command"))
print(file.write(" It allow you to write in  particular file"))

file=open("file1.txt","r")
print(file.read(6))

file=open("file1.txt","r")
print(file.read(6))

file = open("gi.txt","a")
print(file.write("this will add line"))
file.close





import pandas as pd


details = pd.DataFrame({
	'ID': [101, 102, 103, 104, 105,
		  106, 107, 108, 109, 110],
	'NAME': ['Jagroop', 'Praveen', 'Harjot',
			'Pooja', 'Rahul', 'Nikita',
			'Saurabh', 'Ayush', 'Dolly', "Mohit"],
	'BRANCH': ['MCA', 'EEE', 'ISE', 'MECH', 'CSE',
			'ECE', 'MBA', 'AERO', 'MCA', 'CIVIL']})

fees_status = pd.DataFrame({   
    'ID': [101, 102, 103, 104, 105,
		   106, 107, 108, 109, 110],
	'PENDING': ['5000', '250', 'NIL',
				'9000', '15000', 'NIL',
				'4500', '1800', '250', 'NIL']})


print(pd.merge(details, fees_status, on='ID'))

print (pd.concat([details, fees_status]))

df = pd.DataFrame(fees_status)
print(df)
df_filtered = df.query('ID>105')
print(df_filtered)



import pandas as pd
df = pd.read_csv('csv.csv')
print(df.to_string())

import pandas as pd
df = pd.read_csv('csv.csv')
print(df)

import pandas as pd
print(pd.options.display.max_rows)


import pandas as pd
data = {
        'name': ['Alice', 'Bob', 'Charles', 'David', 'Eric'],
        'year': [2017, 2017, 2017, 2017, 2017],
        'salary': [40000, 24000, 31000, 20000, 30000]
        }
data1 = pd.DataFrame({
         'Name': ['Billy', 'Brian', 'Bran', 'Bryce', 'Betty'],
         'subject_id':['sub2','sub4','sub3','sub6','sub5'],
         'Marks_scored':[89,80,79,97,88]})

df = pd.DataFrame(data, index = ['Acme', 'Acme', 'Bilbao', 'Bilbao', 'Bilbao'])

print(df)

df_filtered = df.query('salary>30000')
print(df_filtered)


df_filtered = df[(df.salary >= 30000) & (df.year == 2017)]
print(df_filtered)



import numpy as np
#cretaion of 2d array
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr)
#cretaion of 3d array
arrr = np.array([[[1, 2, 3], [4, 5, 6]], [[1, 2, 3], [4, 5, 6]]])
print(arrr)
#searching with index
print('2nd element on 1st row: ', arr[0, 1])
print('Last element from 2nd dim: ', arr[1, -1])
#indexing of 3d array
print(arrr[0, 1, 2])
print(arrr[1, 1:4])
#slicing
print(arrr[1:5:2])
print(arrr[0:2, 1:4])
print(arrr[::2])
#sorting and searching
ar = np.array([9,2,1,5,3,10,33,12,56,78,13,8,6])
print(ar)
print(np.sort(ar))
x = np.searchsorted(ar, [2, 4, 6])
print(x)
#reshaping
arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12])

newarr = arr.reshape(2, 3, 2)

print(newarr)
#splitting of array
import numpy as np
arr = np.array([[1, 2], [3, 4], [5, 6], [7, 8], [9, 10], [11, 12]])
newarr = np.array_split(arr, 3)
print(newarr)


import numpy as np
import matplotlib.pyplot as plt

x = np.arange(0, 3 * np.pi, 0.1)
y_sin = np.sin(x)
y_cos = np.cos(x)

plt.plot(x, y_sin)
plt.plot(x, y_cos)
plt.xlabel('x axis label')
plt.ylabel('y axis label')


class Vehicle:
    def __init__(self, brand, model):  # Constructor demonstrates encapsulation
        self.brand = brand
        self.model = model

    def move(self):  # Method demonstrates encapsulation
        print("Move!")

class Car(Vehicle):  # Inheritance: Car inherits from Vehicle
    pass

class Boat(Vehicle):  # Inheritance: Boat inherits from Vehicle
    def move(self):  # Method overriding demonstrates method overloading
        print("Sail!")

class Plane(Vehicle):  # Inheritance: Plane inherits from Vehicle
    def move(self):  # Method overriding demonstrates method overloading
        print("Fly!")

class Bus(Vehicle):  # Inheritance: Bus inherits from Vehicle
    def move(self):  # Method overriding demonstrates method overloading
        print("Drive on the road!")

car1 = Car("Ford", "Mustang")  # Create a Car object
boat1 = Boat("Ibiza", "Touring 20")  # Create a Boat object
plane1 = Plane("Boeing", "747")  # Create a Plane object
bus1 = Bus("Mercedes", "Sprinter")  # Create a Bus object

for x in (car1, boat1, plane1, bus1):
    print(x.brand)
    print(x.model)
    x.move()  # Polymorphism: Different move methods based on object's class




