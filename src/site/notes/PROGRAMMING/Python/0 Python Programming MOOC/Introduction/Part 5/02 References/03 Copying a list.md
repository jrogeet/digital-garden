---
topic: lists
part: "5.2"
dg-publish: true
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #lists #references 
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python\|00 PROGRAMMING/Python/_Python/Python]] 

---
# 03 Copying a list

--- 

To create an actual separate copy of a list
Create a new list and add each item from the original list in turn:
```python
my_list = [1, 2, 3, 3, 5]

new_list = []
for item in my_list:
    new_list.append(item)

new_list[0] = 10
new_list.append(6)
print("the original:", my_list)
print("the copy:", new_list)
```

A snapshot of the copying process in the visualisation tool:
![Pasted image 20230903115842.png](/img/user/PROGRAMMING/Python/0%20Python%20Programming%20MOOC/Introduction/Part%205/02%20References/attachments/Pasted%20image%2020230903115842.png)
The variable ___`new_list`___ points to a different list than the variable ___`my_list`___.

---
## Easier way: Slice:

An easier way to copy a list is the __Bracket operator__ ___[ ]___,
The notation ___[ : ]___ selects all items in the collection.

As a side effect, it creates a copy of the list:
```python
my_list = [1,2,3,4]
new_list = my_list[:]

my_list[0] = 10
new_list[1] = 20

print(my_list)
print(new_list)
```

