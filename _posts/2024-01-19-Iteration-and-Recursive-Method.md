---
layout: post
title: "Iteration and Recursive Method using Python"
description: Understanding the difference between iteration and recursive method
tags: Python
---
## Iteration and Recursive Method using Python
### Iteration
Iteration means that the process of math or computing is repeated again and again until the last boundary ([Oxford Learner’s Dictionaries](https://www.oxfordlearnersdictionaries.com/definition/english/iteration?q=iteration)). In programming, the iteration process can be described as pseudocode of summation below:

```
total = 0
do index from 1 to 10
	total = total + index
end do

```
It means, the index number will be added from 1 to 10, where the index of 10 is the last boundary. So, from this condition, the initial total is equal to 0 plus by the first index is 1 and we get the new total is 1. It will be repeated to the second index, where the new total will be added to the second index, where the second index is 2. This process will repeat again and again until the last boundary is fulfilled. Then, we get the final summation of the total is 55.

Now, if we have five numbers in a set of data, for example, data = [3,2,5]. Then, we want to sum the whole data from the first number to the fifth number. In a simple way, we can write the pseudocode of the summation below:

```
data = [3,2,5]
total = 0
do index from 1 to 3
	total = total + data(index)
end do
```
and the final total is 10. We then can write the simple summation process in-Python Function program as follows:

#### Program 1
```
def myadd(data):
    n = len(data)
    total = 0
    for index in range(n):
        total = total + data[index]
    return total

# Iteration myadd
data = [3,2,4,6,8]
res = myadd(data)
print("Iteration sum:",res)
```

If we apply the iteration method to a simple mathematical process and the data is not a large number, it will be easy to process and take a short time to process. However, if we apply this method to a complex mathematical process and the data is a huge number, it will take a long time to process. The solution is, that we can use a recursion method to solve the process when a huge number of data is used.

### Recursion
Recursion is the process of repeating the function itself inside the function itself. Let’s illustrate the simple way to understand the recursion method. You want to take your things from each repository room, but you have to find the huge bag first.

You can imagine that in front of you, there is a big door in your storage room. You open that door and you don’t find that bag. Then, you find another door inside the first door, which is the second door. You open the second door and you don’t find that bag again. Then, you find another door again inside the second door. You open the third door and you don’t find that bag again and again. Then, you find another door again and again inside the third door. You open the fourth door and finally, you find the bag and you can take out the bag. The illustration is shown in the figure below

![recursive_img](/img/recursive_img.png)

This process will repeat again and again until the last condition is fulfilled. The last condition of the illustration above is the huge bag in the fourth door. In the fourth door, you take out the bag and put some things inside the bag from each door, from the fourth door to the first door. Finally, you get the all things that you want.

Now, we use the example of iteration data, where data = [3,2,5] to apply in the recursion process. However, for the first example, we take the first two data, where data = [3,2]. So, the recursion process of summation can be written in Python Function as follows:

#### Program 2
```
import numpy as np
def recursive_myadd(data):
    n = len(data)
    data = np.asarray(data)
    if n == 1:
        return data[0]
    else:
        number = data[0]
        next_data = recursive_myadd(data[1:])
        sumres = number+next_data
        return sumres

# Recursive myadd
data = [3,2]
mysum = recursive_myadd(data)
print("Recursive sum\t:",mysum)
```
The result of the recursion process of summation from the program above is 5.

### How does the recursion algorithm of program 2 work?
Program 2 is the simple summation process using the recursion method. The red color in program 2 indicates the main function of summation. We can see, the main function is recursive_myadd(data). This function is called again inside the main function itself with the latest data, where the command is recursive_myadd(data[1:]). Let’s imagine the recursive process based on program 2.

We call the function recursive_myadd(data) where the data = [3,2] in the blue part of program 2. The data have 2 points number and it means n = 2. Then, we get the logical step, if n == 1. It indicates if the n is equal to 1, the result is data[0] which is the first number of data, there is 3 in this case. However, the current number of n is 2, so the logical step is not fit, because n is not equal to 1. Then, the process will go to the other part. In the else part, we take the first data as a number variable which is number = data[0] or number = 3. After that, the main function of recursive_myadd(data) is called again inside the main function itself (orange part) with the new data, where data = data[1:] and the command can be written recursive_myadd(data[1:]). From recursive_myadd(data[1:]) in program 2, the current data is 2 because the number at the first index to the last index of data is only 2 and it has n equal to 1. Then, we get the logical step again from the second call of recursive function, if n == 1. Because n = 1, it means the logical step is fulfilled. In other words, the recursive_myadd(data[1:]) is data[0] where data[0] is 2 and it will be stored in the next_data variable. Finally, the summation result is sumres = number + next_data = 5.

__Tips: The recursion process will start from the base condition or the last condition and will continue to the previous condition that was saved. According to this example, if the data = [3,2,5] then, the summation starts from 5 which is the last data and it will be added by 2 which is the second data. It will produce 7 and will be added by 3, finally we get the final result of summation is 10.__

#### Program 3
```
import numpy as np
def recursive_myadd(data,storedata=[]):
    n = len(data)
    data = np.asarray(data)
    if n == 1:
        print("n is\t\t:",n)
        storedata.append(data[0])
        return data[0],storedata
    else:
        print("n is\t\t:",n)
        number = data[0]
        next_data,save_data = recursive_myadd(data[1:])
        print("Next data\t:",next_data)
        print("Number\t\t:",number)
        sumres = number+next_data
        storedata.extend([number])
        return sumres,storedata

# Recursive myadd
data = [3,2,5]
mysum,store_data = recursive_myadd(data)
print("Data\t\t:",store_data)
print("Length of data\t:",len(store_data))
print("Recursive sum\t:",mysum)
```
Program 3 is expanded from program 2 but still has the same purpose and the data has been updated to become data = [3,2,5]. By reading and understanding Program 3, maybe you can imagine how the recursion function works. So, the result of program 3 in the figure below

![recursive_result](/img/recursive_img_2.png)

### The advantages of the recursion method
1.	Reduces the length of program,
2.	The code is clean and elegant
3.	Generating sequence is easier than using nested iteration.

### The disadvantages of the recursion method
1.	Hard to understand,
2.	Difficult to trace and bug,
3.	In Some cases, recursion requires extra memory but it takes  a short time to process.

### References
1. https://www.trytoprogram.com/python-programming/python-recursive-function/
2. https://www.edureka.co/blog/recursion-in-python/
